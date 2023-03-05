# Basic socket programming function and datatype in UNIX

### Datatype
* struct sockaddr_in obj;
* struct sockaddr obj;

### Function
* [SOCKET socket(int domain, int type, int protocol);](#socket())
* [int connect(SOCKET s, const struct sockaddr *peer, int peer_len);](#connect())
* [int recv(SOCKET s, void *buf, size_t len, int flags);](#recv())
* [int send(SOCKET s, const void *buf, size_t len, int flags);](#send())
* [int recvfrom(SOCKET s, void *buf, size_t len, int flags, struct sockaddr *from, int *fromlen);](#revfrom())
* [int sendto(SOCKET s, const void *buf, size_t len, int flags, const struct sockaddr *to, int tolen);](#sendto())
* [int bind(SOCKET s, const struct sockaddr *name, int namelen);](#bind())
* [int listen(SOCKET s, int backlog);](#listen())
* [SOCKET accept(SOCKET s, struct sockaddr *addr, int *addrlen);](#accept())

### socket()
***Description -*** This function used to create a socket 

***Return -*** Socket descriptor on success and -1 on failure

***Parameter -***

* **int domain -** Often used domain are *AF_INET* and *AF_LOCAL*
* **int type -** The type of socket *(SOCK_STREAM, SOCK_DGRAM, SOCK_RAW)*
* **int protocol -** Specify which protocol to use, for *SOCK_STREAM* (default- 0),*SOCK_RAW* has different protocol

### connect()
***Discription -*** This function is used to connect a socket to peer sockaddr

***Return -*** 0 on success, -1 on failure

***Parameter -***

* **SOCKET s -** Socket object
* **const struct sockaddr\* peer -** Struct that store address and port number
* **int peer_len -** lenght of the struct sockaddr

### recv()
***Discription -*** This function is used to read from *TCP* socket

***Return -*** number of bytes transferred on success,-1 on failure

***Parameter -***

* **SOCKET s -** Socket object
* **void\* buf -** Message buffer
* **size_t len -** Length of the buffer
* **int flags -** *(MSG_OOB, MSG_PEEK, MSG_DONTROUTE)* 

### send()
***Discription -*** This function is used to write to *TCP* socket

***Return -*** number of bytes transferred on success,-1 on failure

***Parameter -***

* **SOCKET s -** Socket object
* **const void\* buf -** Message buffer
* **size_t len -** Length of the buffer
* **int flags -** *(MSG_OOB, MSG_PEEK, MSG_DONTROUTE)* 

### recvfrom()
***Discription -*** This function is used to read from *UDP* socket

***Return -*** number of bytes transferred on success,-1 on failure

***Parameter -***

* **SOCKET s -** Socket object
* **void\* buf -** Message buffer
* **size_t len -** Length of the buffer
* **int flags -** *(MSG_OOB, MSG_PEEK, MSG_DONTROUTE)* 
* **struct sockaddr\* from -** Struct that store address and port number
* **int fromlen -** Length of the struct sockaddr from

### sendto()
***Discription -*** This function is used to write to *UDP* socket

***Return -*** number of bytes transferred on success,-1 on failure

***Parameter -***

* **SOCKET s -** Socket object
* **const void\* buf -** Message buffer
* **size_t len -** Length of the buffer
* **int flags -** *(MSG_OOB, MSG_PEEK, MSG_DONTROUTE)*
* **struct sockaddr\* to -** Struct that store address and port number
* **int tolen -** Length of the struct sockaddr from

### bind()
***Discription -*** This function is used to bind the socket to address and port

***Return -*** 0 on success, -1 on failure

***Parameter -***

* **SOCKET s -** Socket object
* **const struct sockaddr \*name -** struct that store address and port number
* **int namelen -** lenght of the struct sockaddr name 

### listen()
***Discription -*** This function is used to mark the socket to listen

***Return -*** 0 on success,-1 on failure

***Parameter -***

* **SOCKET s -** Socket object
* **int backlog -** Max number of connection that can be queued waiting for application to accept them

### accept()
***Discription -*** This function is used to accept a socket connection

***Return -*** SOCKET of socket is OK, -1 on failure

***Parameter -***

* **SOCKET s -** listening socket object
* **struct sockaddr\* addr -** peer address
* **int* addrlen -** size of peer address

