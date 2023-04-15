# Commands

## Basic

- `pwd`
  - print current working directory
- `clear`
  - clear the terminal
  - `ctrl + l` also works
- `cd`
  - change directory
  - `cd ..`
    - go up one directory
  - `cd ~`
    - go to home directory
  - `cd /`
    - go to root directory
  - `cd -`
    - go to previous directory
  - slash compares to root directory, for relative path, use `cd =name=`
- `ls`
  - list directory contents
  - `ls =path=`
    - to list contents of a directory of a certain path
  - `ls --ignore=*.txt`
    - ignore all files with .txt extension
    - short of --ignore is -I
  - `ls -l`
    - long form output
  - `ls -a`
    - show hidden files
  - `ls -lsah`
    - power weapon
- `mkdir =directoryname=`
  - make directory (folder)
  - `mkdir -p =directoryname=/=nesteddir=/=nesteddir2=`
    - make nested directories
- `touch =filename=`
  - create a file if it does not exist
  - if the file exists, it updates the timestamp (modification time) nothing else.
- `rm =filename=`
  - remove a file
  - `rm -r =directoryname=`
    - remove a directory
  - `rm -rf =directoryname=`
    - remove a directory and all its contents
- `cp =filename= =newfilename=`
  - copy a file
  - `cp -r =directoryname= =newdirectoryname=`
    - copy a directory
- `mv =filename= =newfilename=`
  - rename a file
  - `mv =filename= =directoryname=`
    - move a file to a directory
- `which =command=`
  - where is the command located i am running
- `echo =hi=`
  - print a string to the terminal
- `=anything= --help`
  - get help for a command

> --=something= is called a flag
> there are generally two types of writing flags -short and --long way

## Intermediate

> Use arrow keys to navigate through the history of commands and tab to autocomplete

- Reverse Search
  - `ctrl + r`
    - search through history of commands
    - continue to press `ctrl + r` to go through the deep history
    - hit arrow to paste the command in the terminal to be editable
- Bash History
  - `tail ~/.bash_history`
    - view the history of commands
    - tail outputs the last 10 lines of a file
- Copy and Paste
  - ctrl + c and ctrl + v have different functions in the terminal
  - `ctrl + shift + c`
    - copy
  - `ctrl + shift + v`
    - paste
- `!!`
  - runs the last command
- `yes`
  - spams the terminal with yes
- `tar -cf =filename.tar= =multipleFilesAndFolders=`
  - .tar file is like .zip file or .rar file
  - zip and rar file are somewhat compressed but tar is not compressed
  - `tar -zcf filename.tar.gz =multipleFilesAndFolders=`
    - for compression
  - `tar -xzf =filename.tar.gz= -C =directoryname=`
    - extract the tar file to a directory
    - -C flag is used to specify the directory, if not specified it will extract to the current directory

## Interacting with Files

- `less =filename=`
  - read the file. writting cannot be done
  - hit `q` to quit
  - it is good for long files.
- `more =filename=`
  - it is similar to less but it is not as good
- `man =programname=`
  - show the manual of a program in depth.
  - if you want in depth guide use man, or use --help for a quick guide
- `cat =filename=`
  - also used for reading files
- `tail =filename=`
  - show the last 10 lines of a file
  - `tail -n =number= =filename=`
    - show the last =number= lines of a file
  - `tail -f =filename=`
    - show the last 10 lines of a file and keep updating as the file is updated
    - `ctrl + c` to quit
- `head =filename=`
  - vice versa of tail
  - show the first 10 lines of a file
  - `head -n =number= =filename=`
    - show the first =number= lines of a file
