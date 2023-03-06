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
	- 
