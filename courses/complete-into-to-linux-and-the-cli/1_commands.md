# Commands

## Basic

```bash
pwd
  # print current working directory
```

```bash
clear
  # clear the terminal
  # `ctrl + l` also works
```

```bash
cd
  # change directory
    cd ..
      # go up one directory
    cd ~
      # go to home directory
    cd /
      # go to root directory
    cd -
      # go to previous directory
```

> slash compares to root directory, for relative path use `cd =name=`

```bash
ls
  # list directory contents
    ls =path=
      # to list contents of a directory of a certain path
    ls --ignore=*.txt
      # ignore all files with .txt extension
      # short of --ignore is -I
    ls -l
      # long form output
    ls -a
      # show hidden files
    ls -lsah
      # power weapon
```

```bash
mkdir =directoryname=
  # make directory (folder)
    mkdir -p =directoryname= / =nesteddir= / =nesteddir2=
      # make nested directories
```

```bash
touch =filename=
  # create a file if it does not exist
  # if the file exists, it updates the timestamp (modification time) nothing else.
  # multiple files can be given
```

```bash
rm =filename=
  # remove a file
    rm -r =directoryname=
      # remove a directory
    rm -rf =directoryname=
      # remove a directory and all its contents
```

> `r` stands for recursive

```bash
cp =filename= =newfilename=
  # copy a file
    cp -r =directoryname= =newdirectoryname=
      # copy a directory
```

```bash
mv =filename= =newfilename=
  # rename a file
    mv =filename= =directoryname=
      # move a file to a directory
```

```bash
which =command=
  # where is the command located i am running
```

```bash
echo =string=
  # print a string to the terminal
```

> string can be with or without quotes, sometimes quotes are needed

```bash
=anything= --help
  # get help for a command
```

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

```bash
!!
  # runs the last command
```

```bash
yes
  # spams the terminal with yes
    `yes y` or `yes n` or `yes =anything=`
      # spams the terminal with =anything=
```

```bash
tar -cf =filename.tar= =multipleFilesAndFolders=
  # .tar file is like .zip file or .rar file
  # zip and rar file are somewhat compressed but tar is not compressed
    tar -zcf filename.tar.gz =multipleFilesAndFolders=
      # for compression
    tar -xzf =filename.tar.gz= -C =directoryname=
      # extract the tar file to a directory
```

> `-C` flag is used to specify the directory, if not specified it will extract to the current directory
> `&` is used at the end of the command and it takes the process to the background

## Advanced

```bash
ps aux
# list all currently running processes (ps = process status)
```

## Wildcards

these wildcards expansion is done by bash not any specific command so these will work with any command

- `touch file{1,2,3,4}.txt`
  - file1.txt file2.txt file3.txt file4.txt will be created
  - `touch file{1..20}.txt`
    - file1.txt file2.txt . . . file20.txt will be created
    - can be used with letters too
- `echo {a..z}`
  - a b c d e f g h i j k l m n o p q r s t u v w x y z
  - `echo {1..5} {a..e}`
    - 1 2 3 4 5 a b c d e
  - `echo {1..5}{a..e}`
    - 1a 1b 1c 1d 1e 2a 2b 2c 2d 2e 3a 3b 3c 3d 3e 4a 4b 4c 4d 4e 5a 5b 5c 5d 5e
  - `echo {1..10..2}`
    - 1 3 5 7 9
- `*`
  - matches any number of characters
  - `ls *.txt`
    - list all files with .txt extension
  - `ls file-*`
    - list all files starting with file-
  - `ls file?`
    - will match only one character after file
    - can be used multiple file like ?? to match two characters
- `\` escape character can be used anywhere to bypass the meaning of a special character

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
