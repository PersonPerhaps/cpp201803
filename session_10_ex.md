# Session 10

All the following exercises will have to be pushed to your personal account
in https://home.tuxlinuxien.com:9999/

## requirements

Your folder should be called **session_10_ex** and MUST be **private**. Any
public repository will be removed without notice. No need to tell you the score
that goes with it.

Your path will look like
https://home.tuxlinuxien.com:9999/ **student id** /session_10_ex

Add a file called `.gitignore` at the root of your repository to make sure you
don't push unwanted files.

## required files

* server.cpp
* server.hpp
* client.cpp
* client.hpp

## project

The goal of this project will be to implement a server AND a client in C++
using TCP/IP. Even if we will be using C libraries, our implementation
will be achieved with C++.

### server

Our server class doesn't need to support multiple users. The server will
however have to wait for a client to connect, receive data, and write it down
to a file.

```c++
class Server {
public:
    Server(const int port, ofstream &out_file);
    ~Server();
    void run();
private:
    // anything you need to make it work.
}
```

* `Server(const int, ofstream &)` will create a new server socket.
* `~Server()` will close the server socket.
* `run()` will wait for a client indefinitely. This method only exits when
the client stops sending data.

The server will listen on all the network interfaces -> `0.0.0.0`

### client

Our client will have to create a one-shot socket to a server, send a file, then
shut itself down properly.

```c++
class Client {
public:
    Client(const string host, const int port, ifstream &in_file);
    ~Client();
    void senddata();
private:
    // anything you need to make it work.
}
```

* `Client(const string, const int, ifstream &);` will create the socket to a
desired server named by it **host** and **port**.
* `~Client()` will close the socket to the server.
* `senddata()` will read the file **in_file** and send all the content to the
server.

### error management

We know that network programming is a source of error.

If the server cannot bind a given port, the server constructor will have to
throw an exception type `const std::string` which says `bind error 9999` where
`9999` will have to be replaced by the port given in parameter.

If the client cannot connect to a server, the client constructor will have to
throw an exception type `const std::string` which says
`connect error 127.0.0.1:9999` where `127.0.0.1` and `9999` are the host and
port given in parameter.

Once a connection is made between 2 nodes, we can consider that it will NOT
break. To make it simple `Client::send()` and `Server::run()` will NEVER have
to break.

## info

We will have to make sure that we don't have any memory leak. Any allocated
memory MUST be freed.

Your any socket opened MUST be closed.

I will make sure the **out_file** and **in_file** are ALWAYS valid.

## warnings

* break the server then I will break your fingers.
* any memory leak will lead to 0/100.
* any use of malloc/alloc/realloc/free will lead to 0.

## tips

* read this whole document a second time.
* read this whole document a third time.
* baidu is your friend during your homework, I am not. Asking for help while
you could have got the solution on baidu will **cost** you points.

## cheat

I will consider you have cheated if:

* you have copied partially/entirely code from another student.
* you have copied partially/entirely code from Internet.
