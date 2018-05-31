# Session 11

All the following exercises will have to be pushed to your personal account
in https://home.tuxlinuxien.com:9999/

## requirements

Your folder should be called **session_11_ex** and MUST be **private**. Any
public repository will be removed without notice. No need to tell you the score
that goes with it.

Your path will look like
https://home.tuxlinuxien.com:9999/ **student id** /session_11_ex

Add a file called `.gitignore` at the root of your repository to make sure you
don't push unwanted files.

## required files

* Makefile
* \*.cpp
* \*.hpp

## project

The goal of this project will be to implement a very simple ftp server.

You are free to arrange your source code the way you like so you can add as many
sources files you need to complete this exercise.

You can reuse the code from the **session_10_ex** to make this exercise faster
but don't copy it from another student otherwise this will be considered as
cheat.

### Makefile

Since we have a free implementation, a Makefile is mandatory otherwise the code
won't be compiled.

The Makefile will have to implement the following directives:

* `make`
* `make` compiles the server as `my_tiny_ftp`
* `make target='-DMY_TINY_FTP_VERSION=1'` compiles the server as but set the
`MY_TINY_FTP_VERSION` macro to `1`

Our Makefile doesn't need to support `up-to-date` behavior, so we will have to
recompile the binary every time we run `make` command.

### my_tiny_ftp

#### startup message from C++ macro

`my_tiny_ftp` is the name of the compiled binary from the Makefile.

On startup, `my_tiny_ftp` will have to display the `MY_TINY_FTP_VERSION` macro
value set by default or one we have chosen. The default value will be
`version not set.`.

`my_tiny_ftp` will have only one argument which will be the port we will listen

```sh
$> ./my_tiny_ftp 8080 # listen on port 8080
[...]
```

Example:

```sh
$> make
$> ./my_tiny_ftp 8080
version not set.
# does stuff without printing anything else ... (you shouldn't print this line)


$> make target=-DMY_TINY_FTP_VERSION=1
$> ./my_tiny_ftp 8080
version 1.
# does stuff without printing anything else ... (you shouldn't print this line)

$> make target=-DMY_TINY_FTP_VERSION=55
$> ./my_tiny_ftp 8080
version 55.
# does stuff without printing anything else ... (you shouldn't print this line)
```

#### protocol

We will use a simple protocol that will allow us to choose what files we want to
download from our server.

```
COMMAND!!
```

The `COMMAND` will either be a `file/path`, `stop` or `exit`

Example

```
/home/yoann/file_I_want.png!!/home/yoann/dir/file_I_want.png!!stop!!

// or
/home/yoann/file_I_want.png!!/home/yoann/dir/file_I_want.png!!stop!!

// or
/home/yoann/file_I_want.png!!exit!!

// or
exit!!

// or
stop!!
```

* `<filname>!!` means the server needs to send the desired file to the client.
If the path of the wanted file doesn't exist, you will have to send back to the
client `<filename> not found.\n\n`.
* `stop!!` only closes the socket from the client and waits for another client
to connect.
* `exit!!` closes the socket from the client, the server socket and then
properly shutdowns the server.


## info

* We will have to make sure that we don't have any memory leak. Any allocated
memory MUST be freed.
* Any opened socket MUST be closed.
* The command send will ALWAYS be in a valid format.
* The client will ALWAYS send at least ONE command.
* The server MUST support an unlimited number of commands.
* If the server receives `./foo.cpp!!exit!`, the server should start sending the
files `./foo.cpp` then wait for the `exit!!` command to be fully received.
* if the server only receives `./foo.cpp`, the server should wait until the
command has been fully received.
* if a client closes the connection then stop processing commands and wait
for another client.

## warnings

* Break the server then I will break your fingers.
* Any memory leak will lead to 0/100.
* Any use of malloc/alloc/realloc/free will lead to 0/100.
* Any use or read/write will lead to 0/100.
* Receiving or sending data at 1 Byte at a time will make you loose 50 points.
* If you need to compile your binary with `-W -Wall -Werror`, copy/paste this
for each call to `g++`. if `-W -Wall -Werror` doesn't appear in your Makefile
your score drops to 0/100.
* Debug displayed by the bot will be limited
* Asking me what is inside of a test will makes you loose 20 points.
* The commands sent by the client will be unique for each test
* The testing files will be unique for each test.
* The client will send with random chunk size. (don't expect receiving a full
command at once).
* The client will be able to send a buffer containing many commands at once.

## tips

* read this whole document a second time.
* read this whole document a third time.
* baidu is your friend during your homework, I am not. Asking for help while
you could have got the solution on baidu will **cost** you points.
* read `<sys/socket.h>` documentation
* network is not your friend, so check the returned values of each values
carefully.

## cheat

I will consider you have cheated if:

* you have copied partially/entirely code from another student.
* you have copied partially/entirely code from Internet.
