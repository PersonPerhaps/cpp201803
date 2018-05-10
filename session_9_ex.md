# Session 9

All the following exercises will have to be pushed to your personal account
in https://home.tuxlinuxien.com:9999/

## requirements

Your folder should be called **session_9_ex** and MUST be **private**. Any
public repository will be removed without notice. No need to tell you the score
that goes with it.

Your path will look like
https://home.tuxlinuxien.com:9999/ **student id** /session_9_ex

Add a file called `.gitignore` at the root of your repository to make sure you
don't push unwanted files.

## required files

* Makefile

You can add any source file that you want but DON'T push your binaries.

## my_cat

The goal of this exercise is to rewrite a simple **cat** command that will
replace any `\n` by `$\n` and display the output on **STDOUT**. This is similar
to `cat -e`.

```sh
$> echo "tata" > file1.txt
$> echo "yoyo" > file2.txt
$> ./my_cat file1.txt file2.txt > out.txt
$> cat out.txt
tata$
yoyo$
$>
```

If `my_cat` cannot open a file, we will stop the execution of the program and
display `cannot open file <filename>.` on **STDERR**.

```sh
$> echo "tata" > file1.txt
$> ./my_cat file1.txt file2.txt > out.txt
cannot open file file2.txt.
$> cat out.txt
tata$
$>

#OR

$> echo "tata" > file1.txt
$> ./my_cat file2.txt file1.txt  > out.txt
cannot open file file2.txt.
$> cat out.txt
$>
```

## Makefile

Our binary will HAVE TO be named `my_cat` and it MUST be built with the
`Makefile` provided

```sh
$> make
[...]
$> make
make: Nothing to be done for 'all'.
```

Our Makefile will have to implement the following commands

* `make all` will compile the object files and the binary
* `make` same as `make all`
* `make clean` will remove \*.o and my_cat

To make sure we are using the compilation flags, our makefile will have to
match:

```sh
$> cat Makefile| grep -Po '\-W \-Wall \-Werror'
-W -Wall -Werror
```

If the previous command doesn't display anything, then the Makefile will be
considered invalid.

## info

You will have to make sure that you don't have any memory leak. Any allocated
memory should be freed. ALWAYS.

## warnings

* break the server then I will break your fingers.
* any memory leak will lead to 0/100.
* any use of malloc/alloc/realloc/free will lead to 0.
* any use of open/read/write/close from C stdlib will lead to 0.

## tips

* read this whole document a second time.
* read this whole document a third time.
* baidu is your friend during your homework, I am not. Asking for help while
you could have got the solution on baidu will **cost** you points.

## cheat

**I gave you a second chance if you cheated last time. This
time if you get caught, the score of this exercise AND the score of all your
previous exercises will be divided by 2**

I will consider you have cheated if:

* you have copied partially/entirely code from another student.
* you have copied partially/entirely code from Internet.
