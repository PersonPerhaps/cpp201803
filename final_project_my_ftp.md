my_tar
======

The goal of this project is to implement a ftp client in C++ only using
the standard library.

You can create as many files as you want and you can structure the way you like.

## repository

Your repository will be called **final_project** and should be hosted on my
server.

## tool chain

* make
* g++

## build

Your program will have to be built with **make**, but if no files are changed,
then you need to display:

```
up-to-date
```

## binary

Your **Makefile** will have to generate a binary called **my_ftp**.

## requirements

Your program will have to implement the following commands

```
!
    Preceding a command with the exclamation point will cause the command to execute on the local system instead of the remote system.
?
    Request assistance or information about the FTP commands. This command does not require a connection to a remote system.
ascii
    Set the file transfer mode to ASCII (Note: this is the default mode for most FTP programs).
bell
    Turns bell mode on / off. This command does not require a connection to a remote system.
binary
    Set the file transfer mode to binary (Note: the binary mode transfers all eight bits per byte and must be used to transfer non-ASCII files).
bye
    Exit the FTP environment (same as quit). This command does not require a connection to a remote system.
cd
    Change directory on the remote system.
close
    Terminate a session with another system.
delete
    Delete (remove) a file in the current remote directory (same as rm in UNIX).
dir
    Lists the contents of the remote directory. The asterisk (*) and the question mark (?) may be used as wild cards.
help
    Request a list of all available FTP commands. This command does not require a connection to a remote system.
lcd
    Change directory on your local system (same as CD in UNIX).
ls
    List the names of the files in the current remote directory.
mget
    Copy multiple files from the remote system to the local system.
    Note: You will be prompted for a "y/n" response before copying each file.
mkdir
    Make a new directory within the current remote directory.
mput
    Copy multiple files from the local system to the remote system. (Note: You will be prompted for a "y/n" response before copying each file).
open
    Open a connection with another system.
put
    Copy a file from the local system to the remote system.
pwd
    Find out the pathname of the current directory on the remote system.
quit
    Exit the FTP environment (same as "bye"). This command does not require a connection to a remote system.
rmdir
    Remove (delete) a directory in the current remote directory.
trace
    Toggles packet tracing. This command does not require a connection to a remote system.
```


## implementation

* Your program will have to be compatible with any ftp server and behave the
same way as the command **ftp**.


## presentation

The whole group will have to understand each other's code and should be able to
understand it's logic.
If the whole team is not able to explain how some piece of the project are
working, then each team member will see his personal score divided by 2.

## cheat

```
"Cheating seems to be a relevant term only when one is caught in the act.
Otherwise it is viewed as intelligence, no?"
    — HK-47, Knights of the Old Republic
```

If a single team member has cheated, the presentation is immediately stopped and
you will ALL be assigned the score **0/100**.

## libs

For this project, only the stdlib is allowed. sockets and threads will have to
be manages by yourself and correctly.
