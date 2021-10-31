Socket Programming
========================


.. image:: https://static.javatpoint.com/core/images/socket-programming.png


|
 

listen()
---------

.. code:: 

  NAME
       listen() - listen for connections on a socket
  SYNOPSIS
       #include <sys/socket.h>
       int listen(int sockfd, int backlog);
       
- sockfd is the usual socket file descriptor from the socket() system call.

- backlog is the number of connections allowed on the incoming queue.

- As an example, for the server, if you want to wait for incoming connections and handle them in some way, the steps are: first you listen(), then you accept().

- The incoming connections are going to wait in this queue until you accept() (explained later) them and this is the limit on how many can queue up.

- Again, as per usual, listen() returns -1 and sets errno on error.

- We need to call bind() before we call listen() or the kernel will have us listening on a random port.


|

accept()
-----------

.. code:: 

  NAME
       accept() - accept a connection on a socket
  SYNOPSIS
       #include <sys/types.h>
       #include <sys/socket.h>
       int accept(int sockfd, struct sockaddr *addr, int *addrlen);
       
- sockfd is the listen()ing socket descriptor.

- addr will usually be a pointer to a local struct sockaddr_in.  This is where the information about the incoming connection will go (and with it you can determine which host is calling you from which port).

- addrlen is a local integer variable that should be set to sizeof(struct sockaddr_in) before its address is passed to accept().

- accept() will not put more than that many bytes into addr.  If it puts fewer in, it’ll change the value of addrlen to reflect that.

- accept() returns -1 and sets errno if an error occurs.

- Basically, after listen(), a server calls accept() to wait for the next client to connect.  accept() will create a new socket to be used for I/O with the new client.  The server then will continue to do further accepts with the original sockfd.

- When someone try to connect() to your machine on a port that you are listen()ing on, their connection will be queued up waiting to be accepted.  You call accept() and you tell it to get the pending connection.

- It’ll return to you a new socket file descriptor to use for this single connection.

- Then, you will have two socket file descriptors where the original one is still listening on your port and the newly created one is finally ready to send() and recv().










`ref <https://www.tenouk.com/Module39c.html>`_





