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
