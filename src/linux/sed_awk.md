## Misc Commands

### Command `sort`
sorts file by lines.
`sort -n file.txt` sorts numerically instead of lexicographicaly.

<https://www.man7.org/linux/man-pages/man1/sort.1.html>

### Command `uniq`
only detects repeated lines that are adjacent.

<https://man7.org/linux/man-pages/man1/uniq.1.html>

### Command `shuf`
generates a random permutation of a file.
`shuff -n 10 file.txt` gets a sample of 10 lines

<https://man7.org/linux/man-pages/man1/shuf.1.html>

## Command `awk`
AWK is an interpreted scripting language for text processing. The command `awk` is used for running AWK scripts. However today we'll be only covering inline definitions of AWK scripts.

* `awk '{print}' cat_crimes.csv` prints all lines of `cat_crimes.csv` (similar to the `cat` command)
* `awk -F, '{print $1}' cat_crimes.csv` specifies a separator to be `','` and prints the first column `'$1'`.
* `awk -F, '{print $1, $3}' cat_crimes.csv` prints the first column `'$1'` and the third column `'$3'`.
* `awk -F, '/Arson/ {print $1}' cat_crimes.csv` will print the name of all cats that have committed arson (does a word matching based on "Arson")

### Awkward World (obligatory hello, world!)
Command `awk 'BEGIN {print "Hello, World!"}'` prints `Hello, World!`
* `BEGIN` specifies that the following part of the script should be run first.

<https://www.gnu.org/software/gawk/manual/gawk.html#Getting-Started>

## Command `sed`
Sed is a stream editor. Sed is also a scripting language with the same name. Sed supports pattern matching using basic regular expressions.

### Text replacement
(Try this in neovim for better visualization using the `:%s/old_string/new_string/`)

Command `sed -i 's/cat/fox/g' animals.txt` finds and replaces every instance of `cat` by a `fox` in a file called `animals.txt`.
* Argument `-i` makes replacement in place else it just outputs into stdout and we can redirect the output to a file `sed 's/cat/fox/g' animals.txt > new_animals.txt`.
* The `g` in `s/cat/fox/g` means replace every occurrence of the pattern in a line.

### Printing
(Try this in neovim for better visualization using the `:/pattern/`)

Command `sed -n '/fox/p' animals.txt` finds and prints all the lines containing `fox`.
* Argument `-n` suppresses output of a file (by default it prints every line, this will only print lines matching the pattern)
* The `p` in `/fox/p` means print.

### Deleting
Command `sed '/dog/d' animals.txt` deletes every occurrence of the word `dog`.

<https://www.gnu.org/software/sed/manual/sed.html>
