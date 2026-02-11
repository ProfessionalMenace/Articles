## Pipes, Redirection and Tee ☕

### Pipes
Operator pipe `|` takes standard output of the left command and puts it into standard input of the right command.
Example: You can pipe the output of a file into grep and sort it `cat 'logs.txt' | grep "ERROR" | sort`.
You can also redirect the standard output and stderr using the `|&` command

<https://www.gnu.org/software/bash/manual/html_node/Pipelines.html>

### Redirection
When you don't want some program spam you terminal with a lot of text you can simply redirect the standard output into `/dev/null` (special file that discards everything you try writing into it)

<https://man7.org/linux/man-pages/man4/zero.4.html>

### Tee
Tee redirects output to both standard output and a file. I honestly use this a lot when compiling `make | tee log.txt`

<https://man7.org/linux/man-pages/man1/tee.1.html>
