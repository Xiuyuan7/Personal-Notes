# UDP Socket

## Overview

![image-20220218190255719](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220218190255719.png)

## Client

```python
# python udp_client.py [server_hostname] [server_port] [messages]

import socket
import sys


def body():
    # argument 1
    HOSTNAME = sys.argv[1]
    # check hostname and convert to IP address
    try:
        HOST = socket.gethostbyname(HOSTNAME)
    except socket.error as e:
        # handle error condition
        print("Unknown hostname: %s" % HOSTNAME)

    # argument 2, convert to integers
    PORT = int(sys.argv[2])

    # build address data structure
    sin = (HOST, PORT)

    # define buffer size
    BUFFER = 1024

    # argument 3, convert to bytes
    msg = sys.argv[3].encode()

    # create a socket
    try:
        # IPv4, Datagram Socket, Default Internet
        sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM, 0)
    except socket.error as e:
        print('Failed to create socket.')
        sys.exit()

    # send messages
    try:
        sock.sendto(msg, sin)
    except socket.error as e:
        print('Failed to send messages.')
        sys.exit()

    # receive messages
    try:
        msg_ret, sin_ret = sock.recvfrom(BUFFER)
    except socket.error as e:
        print('Failed to receive messages.')
        sys.exit()

    # print messages
    print("Message from server: %s" % msg_ret.decode())

    # close socket
    try:
        sock.close()
    except socket.error as e:
        print('Failed to close socket.')
        sys.exit()


# check arguments
if __name__ == '__main__':
    if len(sys.argv) == 4:
        body()
    else:
        print('Wrong input arguments, please enter 3 arguments.')

```



## Server

```python
# python udp_server.py [server_port]

import socket
import sys


def body():
    # get server hostname LAPTOP-GH7JJJNQ
    HOSTNAME = socket.gethostname()
    print(HOSTNAME)
    # check hostname and convert to IP address
    try:
        HOST = socket.gethostbyname(HOSTNAME)
    except socket.error as e:
        print("Unknown hostname: %s" % HOSTNAME)
        sys.e

    # argument 1, convert to integers
    PORT = int(sys.argv[1])

    # build address data structure
    sin = (HOST, PORT)

    # define buffer size
    BUFFER = 1024

    # create a socket
    try:
        # IPv4, Datagram Socket, Default Internet
        sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM, 0)
    except socket.error as e:
        print('Failed to create socket.')
        sys.exit()

    # bind socket address with socket descriptor
    try:
        sock.bind(sin)
    except socket.error as e:
        print('Failed to bind socket.')
        sys.exit()

    # receive messages
    try:
        # bytes msg, client address (host, port)
        msg, client_addr = sock.recvfrom(BUFFER)
    except socket.error as e:
        print('Failed to receive messages.')
        sys.exit()

    # print received messages and client address
    print('Server received: %s' % msg.decode())
    print(f'Message from {client_addr}')

    # send messages
    msg = b"Message received."
    try:
        sock.sendto(msg, client_addr)
    except socket.error as e:
        print('Failed to send message.')
        sys.exit()

    # close socket
    try:
        sock.close()
    except socket.error as e:
        print('Failed to close socket.')
        sys.exit()


# check arguments
if __name__ == '__main__':
    if len(sys.argv) == 2:
        body()
    else:
        print('Wrong input arguments, please enter 1 arguments.')


```



# TCP Socket

## Overview

![image-20220218190344204](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220218190344204.png)

1. Echo Server

echo-server.py

```python
#!/usr/bin/env python3

import socket

# standard loopback interface address (localhost).
# accept connections on all available IPv4 interfaces if pass an empty string.
HOST = '127.0.0.1'

# port should be an integer from 1-65535 (0 is reserved).
# port to listen on (non-privileged ports are > 1023)
PORT = 65432

# socket.socket() creates a socket object.
# AF_INET is the Internet address family for IPv4.
# SOCK_STREAM is the socket type for TCP.
# The with statement is used with socket.socket() to automatically close the socket at the end of the block.
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    # bind() associates the socket with a specific network interface and port number.
    s.bind((HOST, PORT))
    # listen() enables a server to accept() connections.
    # listen() has a backlog parameter. It specifies the number of unaccepted connections that the system will allow before refusing new connections.
    s.listen()
    # accept() blocks and waits for an incoming connection.
    # accept() returns a new socket object representing the connection and a tuple holding the address of the client when a client connects.
    # The tuple will contain (host, port) for IPv4 connections or (host, port, flowinfo, scopeid) for IPv6.
    conn, addr = s.accept()
    # The with statement is used with conn to automatically close the socket at the end of the block.
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                # the loop terminates if data is an empty bytes object, b''.
                break
            # echo back all data.
            conn.sendall(data)
```

## Echo Client

echo-client.py

```python
#!/usr/bin/env python3

import socket

HOST = '127.0.0.1'  # The server's hostname or IP address
PORT = 65432        # The port used by the server

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b'Hello, world')
    data = s.recv(1024)

print('Received', repr(data))
```

## Run Files

Open a terminal in the working directory and run the server.

```shell
$ ./echo-server.py
```

Open another terminal and run the client.

```shell
$ ./echo-client.py 
```

## View Socket State

To see the current state of sockets on your host.

```shell
$ netstat -an
Active Internet connections (including servers)
Proto Recv-Q Send-Q  Local Address          Foreign Address        (state)
tcp4       0      0  127.0.0.1.65432        *.*                    LISTEN
```

```shell
$ lsof -i -n
COMMAND     PID   USER   FD   TYPE   DEVICE SIZE/OFF NODE NAME
Python    67982 nathan    3u  IPv4 0xecf272      0t0  TCP *:65432 (LISTEN)
```

`lsof` gives you the `COMMAND`, `PID` (process id), and `USER` (user id) of open Internet sockets when used with the `-i` option.