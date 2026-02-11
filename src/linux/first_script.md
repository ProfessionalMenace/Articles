## First Bash Shell Script
Run `bash --version` to see the version of you bash(Bourne-Again SHell) or if it's even installed. 
> Bash is the shell, or command language interpreter, for the GNU operating system.

There are two common ways to run a script:
1. `bash script.sh` (maybe preferred)
2. making it executable using `chmod +x script.sh` and running it `./script.sh`

### First script
script.sh:
```sh
#!/usr/bin/env bash
# specifies what interpreter to use 
# https://en.wikipedia.org/wiki/Shebang_(Unix)

# echo -- displays a line of text
# obligatory hello, world!!!
echo 'Hello, World!'

# To pass any arguments into this script you can use $1 to get the first argument
echo "script name $0"
echo "first argument $1"
echo "number of arguments $#"
echo "all argument $@"
```
When running this script with `./first_script.sh meow1 meow2 meow3 meow4` you should get this output
```
Hello, World!
script name ./script.sh
first argument meow1
number of arguments 4
all argument meow1 meow2 meow3 meow4
```

### Quotes
In bash there actually is a difference between `' '` and `" "` (and also \` \` later). Consider this example:
```sh
echo "Hello, $1" # this uses the first argument
echo 'Hello, $1' # this prints the string Hello, $1
```

### IF statement
<https://www.gnu.org/software/bash/manual/bash.html#Bash-Conditional-Expressions-1>
<https://www.gnu.org/software/bash/manual/bash.html#Conditional-Constructs-1>

Example 1: a simple utility that checks if the first argument is "cat".
```sh
if [[ $1 == "cat" ]] then
    echo "Yaaaaaaaaay kitty"    
else
    echo "Not kitty :("
fi
```

Exit statuses fall between 0 and 255

Example 2: Check if the first argument is not empty.
```sh
if [[ -n $1 ]] then
    echo "first argument $1"    
else
    echo "No argument"
fi
```

Example 3: Check if the first argument is a valid path to a file.
```sh
if [[ -f $1 ]] then
    echo "File exists"
else
    echo "File does not exist"
    exit 1 # signifies failure
fi
```

### For loop
<https://www.gnu.org/software/bash/manual/bash.html#Conditional-Constructs-1>

Example 1: Print animal in a list of animals
```sh
for animal in cat dog fox penguin; do
    echo $animal
done
```

Example 2: For i in range 0 to 10 (inclusive)
```sh
for i in {1..10}; do
    echo "Meow!"
done
```

Example 3: C-like for loop (supports arithmetic expressions)
```sh
for (( i=0 ; i<10; i+=1 )); do
    echo $1
```

Example 4: Arguments & Arithmetic expansion
```sh
sum=0
#for all arguments
for num in "$@"; do
    sum=$((sum + num)) # $((...)) arithmetic expansion
done
echo "The total sum is: $sum"
```
