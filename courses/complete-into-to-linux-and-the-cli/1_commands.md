# Commands

## Basic

```bash
# print current working directory
pwd
```

```bash
# clear the terminal
clear
```

> `ctrl + l` can also be used for clearing the screen

```bash
# change directory
cd

# go up one directory
cd ..

# go to home directory
cd ~

# go to root directory
cd /

# go to previous directory
cd -
```

> slash compares to root directory, for relative path use `cd <name>`

```bash
# list directory contents
ls

# to list contents of a directory of a certain path
ls <path>

# ignore all files with .txt extension
ls --ignore=*.txt

# 🔴 short of --ignore is -I

# long form output
ls -l

# show hidden files
ls -a

# power weapon
ls -lsah
```

```bash
# make directory (folder)
mkdir <directoryname>

# make nested directories
mkdir -p <directoryname> / <nesteddir> / <nesteddir2>
```

```bash
# create a file if it does not exist
touch <filename>

# 🔴 multiple files can be given
```

> if the file exists, it updates just updates the modification time.

```bash
# remove a file
rm <filename>

# remove a directory
rm -r <directoryname>

# remove a directory and all its contents
rm -rf <directoryname>
```

> `r` stands for recursive and `f` stands for force.

```bash
# copy a file
cp <filename> <newfilename>

# copy a directory
cp -r <directoryname> <newdirectoryname>
```

> Files can also be copied with cat command, see [streams.md](./2_streams.md)

```bash
# move a file to a directory
mv <fileName> <directoryName>

# rename a file
mv <fileName> <newFileName>
```

```bash
# where is the command stored
which <command>
```

```bash
# print a string to the terminal
echo <string>
```

> string given to `echo` can be with or without quotes, if there are no variables (`$VARIABLE`) in the string, it is recommended to use quotes.

```bash
# print the current user
whoami
```

```bash
<anyCommand> --help
  # get help for a command
```

> Anything after `-` or `--` is called an option or a flag

> there are generally two types of writing flags -short and --long way

## Intermediate

> Use arrow keys to navigate through the history of commands and tab to autocomplete

#### Reverse Search

- `ctrl + r`
  - search through history of commands
  - continue to press `ctrl + r` to go through the deep history
  - hit arrow to paste the command in the terminal to be editable

#### Bash History

- `tail ~/.bash_history`
  - view the history of commands
  - tail outputs the last 10 lines of a file

#### Copy and Paste

- ctrl + c and ctrl + v have different functions in the terminal
- `ctrl + shift + c`
  - copy
- `ctrl + shift + v`
  - paste

---

```bash
# run the last command
!!
```

```bash
# spams the terminal with 'yes'
yes

# spams with 'y'
yes y

# spams with 'n'
yes n

# spams with 'anything'
yes <anything>
```

## Advanced

```bash
ps aux
# list all currently running processes (ps = process status)
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
