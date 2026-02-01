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

### Control flow statements
let's create a simple utility that checks if the first argument is "foo"
```sh
#!/usr/bin/env bash

# if the first argument is "cat" print "Yaaaaaay" kitty else exit the file
if [[ $1 == "cat" ]] then
    echo "Yaaaaaaaaay kitty"    
else
    echo "String '$1' does not equal 'cat'"
    exit 1
fi

# for i in set from 1 to 10 print "Meow"
for i in {1..10}; do
    echo "Meow!"
done
```
here should be noted that you can use `if[ $1 == "cat" ]` but it errors out if you pass in `"meow meow"` it errors out (you should try this yourself and see what error message you get).