## Files and Navigation

### Command `pwd`
Command `pwd` prints the current working directory (cwd). It prints the absolute path of the directory your shell process is currently in (useful for debugging).
<https://man7.org/linux/man-pages/man1/pwd.1.html>

### Command `ls`
Command `ls` list directory contents (prints files in cwd). There are few arguments that should interest you:
1. `ls -a` lists all files including dotfiles (file starting with `.`)
2. `ls -l` lists file in a long format (provides extra information like permissions, user, time created, size, ...)
3. `ls -R` lists subdirectories recursively
<https://man7.org/linux/man-pages/man1/ls.1.html?

### Command `cd`
Command `cd` changes directory.
1. `cd ..` changes cwd to it's parent directory
2. `cd coolcats/` changes cwd to the `coolcats/` directory
<https://man7.org/linux/man-pages/man1/cd.1p.html>

### Command `find`
Command `find` simply searches for files (recursively) and prints them to stdout.
1. `find` finds all files in the cwd
2. `find coolcats/` finds all files in `coolcats/` directory
3. `find coolcats/ -name "orange*"` argument `-name` adds option to use pattern matching. This should find all the pictures of orange cats (The string `"orange*"` finds all files starting with `"orange"`)
4. `find coolcats/ -type f` searches only for regular files
<https://man7.org/linux/man-pages/man1/find.1.html>
