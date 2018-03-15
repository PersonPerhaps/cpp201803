my_tar
======

The goal of this project is to implement a http server in C++ only using the
standard library.

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

Your **Makefile** will have to generate a binary called **my_http**.

## requirements

Your program will have to implement the following commands

```
GET
    The GET method requests a representation of the specified resource.
    Requests using GET should only retrieve data and should have no other
    effect. (This is also true of some other HTTP methods.) The W3C has
    published guidance principles on this distinction, saying, "Web application
    design should be informed by the above principles, but also by the relevant
    limitations."

HEAD
    The HEAD method asks for a response identical to that of a GET request, but
    without the response body. This is useful for retrieving meta-information
    written in response headers, without having to transport the entire content.

POST
    The POST method requests that the server accept the entity enclosed in the
    request as a new subordinate of the web resource identified by the URI. The
    data POSTed might be, for example, an annotation for existing resources; a
    message for a bulletin board, newsgroup, mailing list, or comment thread; a
    block of data that is the result of submitting a web form to a
    data-handling process; or an item to add to a database.

PUT
    The PUT method requests that the enclosed entity be stored under the
    supplied URI. If the URI refers to an already existing resource, it is
    modified; if the URI does not point to an existing resource, then the
    server can create the resource with that URI.

DELETE
    The DELETE method deletes the specified resource.

TRACE
    The TRACE method echoes the received request so that a client can see what
    (if any) changes or additions have been made by intermediate servers.

OPTIONS
    The OPTIONS method returns the HTTP methods that the server supports for
    the specified URL. This can be used to check the functionality of a web
    server by requesting '*' instead of a specific resource.

CONNECT
    The CONNECT method converts the request connection to a transparent TCP/IP
    tunnel, usually to facilitate SSL-encrypted communication (HTTPS) through
    an unencrypted HTTP proxy. See HTTP CONNECT tunneling.

PATCH
    The PATCH method applies partial modifications to a resource.

All general-purpose HTTP servers are required to implement at least the GET and
HEAD methods, and all other methods are considered optional by the
specification.
```


## implementation

* SSL implement is NOT required.
* Compression is NOT required.
* Your server MUST to be able server files of any size.
* Your server MUST be able to deal with simultaneous connections without
blocking.
* Your server MUST have at least 2 threads.
* Your server MUST return the proper error messages.
* Your server MUST listen on the the port **80** by default but your SHOULD
allow the user to change it. (e.g `./my_http --port 8080`)
* Your server MUST be able to deal with any recent web browser.

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
