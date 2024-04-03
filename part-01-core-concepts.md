# Part 1: Core Concepts


## Input, output, pipes

The introduction covers `stdin` and `stdout`, how to combine these
commands with `ls`, `less`, and the pipe (`|`):

> **`stdin`**: The stream of input that Linux reads from your keyboard.
>
> **`stdout`**: The stream of output that Linux writes to your display.

``` bash
ls -l ex/ch01
# total 8
# -rw-rw-r--@  1 mjfrigaard  staff  172 Oct 25 18:13 README.md
# drwxrwxr-x@  6 mjfrigaard  staff  192 Oct 25 18:13 command_1_wc
# drwxrwxr-x@  3 mjfrigaard  staff   96 Oct 25 18:13 command_2_head
# drwxrwxr-x@  3 mjfrigaard  staff   96 Oct 25 18:13 command_3_cut
# drwxrwxr-x@  4 mjfrigaard  staff  128 Oct 25 18:13 command_4_grep
# drwxrwxr-x@  3 mjfrigaard  staff   96 Oct 25 18:13 command_5_sort
# drwxrwxr-x@  4 mjfrigaard  staff  128 Oct 25 18:13 command_6_uniq
# drwxrwxr-x@ 22 mjfrigaard  staff  704 Oct 25 18:13 detecting_duplicate_files
# drwxrwxr-x@  3 mjfrigaard  staff   96 Oct 25 18:13 input_output_pipes
```

In the `ex/ch01/command_1_wc` folder, you’ll see `myfile`. If we run
`less` on `myfile`, we see the file displayed one screenful at a time:

``` bash
less ex/ch01/command_1_wc/myfile
# This is my file
```

## Commands

This section has a great definition and description of **commands** in
Linux:

**A program**: An executable program named and executed by a single
word, such as `ls`, or a similar feature built into the shell, such as
cd (called a shell builtin)

**A simple command**: A program name (or shell builtin) optionally
followed by arguments, such as `ls -l /bin`

**A combined command**: Several simple commands treated as a unit, such
as the pipeline `ls -l /bin | less`

### Combining Commands

> “*You can connect the `stdout` of one command to the `stdin` of
> another, so the first command feeds the second.*”

We can connect `ls -l` and `less` using the pipe:

``` bash
ls -l ex/ch01/command_1_wc | less
# total 32
# -rw-rw-r--@ 1 mjfrigaard  staff  325 Oct 25 18:13 animals.txt
# -rw-rw-r--@ 1 mjfrigaard  staff   16 Oct 25 18:13 myfile
# -rw-rw-r--@ 1 mjfrigaard  staff   21 Oct 25 18:13 myfile2
# -rw-rw-r--@ 1 mjfrigaard  staff   31 Oct 25 18:13 test.py
```

List the contents of a large directory with `ls -l`, then pass this to
`less` to make it more human readable.

> “*You can connect these two commands because `ls` writes to `stdout`
> and `less` can read from `stdin`.*”

This chapter covers an intro to six common Linux commands: `wc`, `head`,
`cut`, `grep`, `sort`, and `uniq`

### `wc`

> “*options `-l`, `-w`, and `-c` print only the number of lines, words,
> and characters*”

``` bash
wc ex/ch01/command_1_wc/animals.txt
#        7      51     325 ex/ch01/command_1_wc/animals.txt
```

``` bash
wc -l ex/ch01/command_1_wc/animals.txt
#        7 ex/ch01/command_1_wc/animals.txt
```

``` bash
wc -w ex/ch01/command_1_wc/animals.txt
#       51 ex/ch01/command_1_wc/animals.txt
```

``` bash
wc -c ex/ch01/command_1_wc/animals.txt
#      325 ex/ch01/command_1_wc/animals.txt
```

## `ls` weirdness

The `ls` command will change it’s behavior depending on `stdout` and
`stdin`

If the

``` bash
ls ex/ch01 | cat
# README.md
# command_1_wc
# command_2_head
# command_3_cut
# command_4_grep
# command_5_sort
# command_6_uniq
# detecting_duplicate_files
# input_output_pipes
```

### `head`

``` bash
wc ex/ch01/command_1_wc/animals.txt
#        7      51     325 ex/ch01/command_1_wc/animals.txt
```

### `cut`

### `grep`

### `sort`

### `uniq`

## The Shell

## Variables

## Re-running Commands

## Filesystem
