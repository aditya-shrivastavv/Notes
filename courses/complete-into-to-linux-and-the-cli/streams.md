# Input and Output Streams

## Output Streams (stdout)

As the UNIX Philosophy says, you should assume that the output of something is input for something. Here, we will look at how to redirect the output of a command.

```bash
echo 'some text' 1> file.txt
# New file generated with 'some text' in it
```

```bash
cat oldfile.txt 1> newfile.txt
# New file generated with contents of oldfile.txt in it (**copied**)
```

```bash
`cat oldfile.txt 1>> newfile.txt
# New file generated gets (**appended**) with the content of oldfile.txt
# appends means it adds the content to the end of the file (**new line**)
```

If you understand the standard output of any program you can redirect it to anything. for example `ls` command.

---

- `1>` redirects the stdout (standard output)
- `1>>` redirects the stdout (standard output) and appends it to the file
- `>`, `>>` goes to the file, if the file does not exist, it creates it.

## Standard Error (stderr)

Standard error have a different stream of flow that's why we have to use `2>` to redirect it.

```bash
cat non-existing-file.txt 2> error.txt
# New file generated with the error message in it
```

```bash
ls -lash 2> /dev/null
# Throw the error messages away, I don't care about them
```

`/dev/null` is a special file that discards everything that is written to it, think about it like a dustbin or black hole.

---

- Here also `>` and `>>` works the same way.

> **Note:** Plain `>` and `>>` will redirect both _stdout_ and _stderr_ to the same place.

## Input Streams (stdin)

```bash
- `cat < file.txt`
# Prints the contents of the file
```

```bash
- `grep 'some text' < file.txt`
# Prints the lines that contain 'some text'
```

grep is a command that searches for a pattern in a file

### Example

```bash
grep 'some-text` < file.txt 1> grepout.txt 2> /dev/null
```

grep finds 'some-text' in file.txt and redirects the output to grepout.txt and ignores the errors. so simple right?

## Pipes

Use to connect the output of one command to the input of another command. Can be used in chain.

```bash
cat file.txt | grep 'some text'
# file.txt is the input for grep
```
