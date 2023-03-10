## 1.1 What is the Internet?

- we can describe the Internet on basis of the hardware and software components.
- we can describe the internet in terms of a networking infrastracture that provides services to distributed applications.

	### 1.1.1 **On basis of  software and hardware that runs the internet**
	- devices that connect to the internet are called **hosts** or **end systems**
	- end systems are connected together by a network of **communication links** and **packet switches**. there are many types of communication links, which are made up of different types of physical media, e.g. coaxial cable, copper wire, optical fiber and radio spectrum.
	- the transmission rate of a link measured in **bits/second**.
	- when one end system has data to send to another end system, the sending end system segments the data and adds header bytes to each segment, the resulting packages of information, know as **packets**, are the sent through the network to the destination end system. where they are reassembled into the original data.
	- End systems access the Internet thorugh Internet Service Providers(ISPs).
	- Lower tier ISPs are interconnected through national and international upper-tier ISPs and these upper tier ISPs are connected directly to each other.
	- End systems and other pieces of the internet run protocols that coltrol the sending and receiving of information within the Internet.
	- TCP - Transmission Control Protocol
	- IP - Internet Protocol
	- **TCP/IP** are two of the most important protocols in the Internet
	- **Internet Standards** are developed by the **Internet Engineering Task Force**(IETF), their standards are called **requests for comments**(RFCs)
	
	### 1.1.2 **A Services Description**
	- We can describe the internet as an infrastracture that provides services to applications.
	- distributed applications involve multiple end systems that exchange data with each other
	- Internet applications runs on end systems, they do not run in the packet switches in the network core
	- End system attached to the Internet provide a **socket interface** that specifies how a program running on one end system asks the Internet infrastructure to deliver data to a specific destination program running on another end system.

	### 1.1.3 **what is a protocol?**
	- A network protocol is similar to a human protocol(how we behave and communicate with each other), except that the entities exchanging messages and taking actions are hardware or software components of some device.
	- hardware implemented protocols in two physically connected computers control the flow of bits on the wire between the two network interface cards.
	- congestion-control protocols in end systems control the rate at which packets are transmitted between sender and receiver
	- protocols in routers determine a packet's path form source to destination
	- __*A Protocol defines the format and the order of messeges exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.*__
	- In other words, a protocol is a set of rules and guidelines that govern the communication between devices or systems. It specifies how data is transmitted, how errors are handled, how devices are identified and authenticated, and how different functions are performed. Without protocols, devices would not be able to communicate with each other effectively and efficiently. There are many different types of protocols, including network protocols, transport protocols, application protocols, and security protocols, each with its own specific purpose and functionality.
explain tcp protocol with an exapmple in C.

TCP (Transmission Control Protocol) is a reliable, connection-oriented protocol that provides a reliable and ordered delivery of data between two endpoints. It is one of the core protocols of the Internet Protocol (IP) suite and is used for transmitting data over the internet.

Here's an example of how to use TCP in C:

1. Create a socket: The first step in using TCP is to create a socket, which is an endpoint for communication. In C, you can create a socket using the `socket()` function:

```
int sockfd = socket(AF_INET, SOCK_STREAM, 0);
```

This creates a new socket with the specified address family (`AF_INET` for IPv4), socket type (`SOCK_STREAM` for TCP), and protocol (`0` for default).

2. Connect to a server: To establish a connection with another endpoint (e.g., a server), you need to use the `connect()` function:

```
struct sockaddr_in serv_addr;
serv_addr.sin_family = AF_INET;
serv_addr.sin_port = htons(PORT);
inet_pton(AF_INET, "127.0.0.1", &serv_addr.sin_addr);

if (connect(sockfd, (struct sockaddr *)&serv_addr, sizeof(serv_addr)) < 0) {
    perror("Error connecting to server");
    exit(1);
}
```

This code sets up the address and port of the server you want to connect to (`127.0.0.1` is localhost), converts it to network byte order using `htons()`, and then uses `connect()` to establish a connection.

3. Send and receive data: Once you have established a connection, you can send and receive data using the `send()` and `recv()` functions:

```
char buffer[1024];
int n;

n = send(sockfd, "Hello world", strlen("Hello world"), 0);
if (n < 0) {
    perror("Error sending data");
    exit(1);
}

n = recv(sockfd, buffer, sizeof(buffer), 0);
if (n < 0) {
    perror("Error receiving data");
    exit(1);
}
buffer[n] = '\0';
printf("Received message: %s\n", buffer);
```

This code sends the string "Hello world" over the connection using `send()`, and then receives any incoming data into a buffer using `recv()`. The received data is then printed out.

4. Close the connection: Finally, when you are done with the connection, you should close it using the `close()` function:

```
close(sockfd);
```

This releases any resources associated with the socket.

Overall, this example demonstrates how TCP can be used in C to establish a reliable connection between two endpoints and transmit data between them in an ordered manner.


