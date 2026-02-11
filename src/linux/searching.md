## Searching in files

### Command `cat`
concatenates files and prints them. Let's assume you have a file called `catcrimes.txt` then the command `cat catcrimes.txt` will print all the crimes you cat has committed. But what if your cat has committed thousands of crimes?

<https://www.man7.org/linux/man-pages/man1/cat.1.html>

### Command `head`
prints the first part (the head of the file). Command `head catcrimes.txt` prints first 10 crimes (lines) of a file called `catcrimes.txt`. In case your cat committed more than 10 crimes you can use `head catcrimes.txt -n 100` which prints the first 100 lines.

<https://www.man7.org/linux/man-pages/man1/head.1.html>

### Command `tail`
prints the last part of a file (the tail of the file). Command `tail catcrimes.txt` prints last 10 most recent crimes (lines) of the file called `catcrimes.txt`. (you can again specify the number of lines using the argument `-n` followed by a number)

<https://www.man7.org/linux/man-pages/man1/tail.1.html>

### Command `wc`
prints line count, word count, byte count and a name of each file. Using `wc -l catcrimes.txt` counts the number of crimes (lines) the cat has committed.

### Command `grep` (global, regular expression, print)
prints lines that match patterns. Command `grep "arson" catcrimes.txt` will print all the lines containing the expression `"arson"`. The important arguments are:
1. `grep -i "arson" catcrimes.txt` case insensitive search
2. `grep -r "battery" animal_crimes/"`recursive search on a directory
3. `grep -v "burglary" catcrimes.txt` searches for all lines not matching the pattern
4. `grep -E "conspiracy|cyberbullying" catcrimes.txt` uses extended regular expressions to find the crimes `"conspiracy"` or `"cyberbullying"`
5. `grep -c "theft" catcrimes.txt` prints the count of the lines
6. `grep -n "vandalism" catcrimes.txt` prints lines that match the pattern and their number

<https://www.man7.org/linux/man-pages/man1/grep.1.html>

### Obligatory regex resources
* <https://regexr.com/>
* <https://regexper.com/>
* <https://www.debuggex.com/>
