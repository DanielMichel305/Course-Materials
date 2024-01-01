# Chapter 7 Client-Server

***

## Distibuted Systems

It is a system of computers known as **Hosts**, each host can be at a different physical location connected to each other using communication links.<br>
There exists 2 different types of Hosts the **Client**   which usually is in the desktop, Laptop, mobile, etc.. form factor and a **Server** which is responsible to proccess large data, network traffic and other specific functions.<br>

The Previous is called a Client-Server Architecture where clients are responsible for end user interaction and requesting server services.

###### The Client-Server archetecture is considered to be a **Two Tier** Architecture

***
##### Remember
<details>
<summary> Streams</summary>

##### Streams
Streams are a sequence of bytes representing a flow of data from a data source to a destination such as networked computers.
Steps for initializing any stream:
- Step 1: Open stream.
- Step 2: Read/Write data from/to the data stream.
- Step 3: close the stream.
</details>

<details>
<summary>Addressing on the internet</summary>

Addressing on any network can be done in 2 ways:
- Numeric address such as an IPv4 address.  
- symbolic address which is mapped to a numeric address(ip addr) using a DNS.
###### DNS:
A DNS (Domain Name Service) is a server with a database of all websites/hosts ip addresses mapped to their domain name. A DNS is considered the backbone of the internet!   
 
</details>

***

## Web access in Java 
Web access is done by creating an object of the URL class which is part of the ```java.net.URL``` that needs to be imported.

```java
URL url = new URL(/*URL Goes Here*/);
```
#### Note: 
When Entering a URL the protocol in which we access the server must be explicitly specified.
Example: ```WWW.google.com``` wont work. Instead, the url must be in the format ```https://www.google.com```.

***

## Ports 
A Port number is a number that allows computers on a network running multiple programs to have their programs communicate at the same time without anny conflict.
It also allows Clients to request specific content/data on a single server. Likewise, a server can use ports to listen for a specific type of connections/requests.<br>

Think of a Port as channel inbound/outbound from a host where hosts can communicate on an agreed upon port.

<table>
    <tr>
    <th>Service</th>
    <th>Port</th>
    </tr>
    <tr>
    <th> HTTP</th>
    <th>80</th>
    </tr>
    <tr>
    <th> SSH</th>
    <th> 22</th>
    </tr>
    <tr>
    <th> RDP</th>
    <th>3389</th>
    </tr>
</table>
<br>

***

## Sockets

Sockets are the Software concept that links a port number and an ip address.

When A Client wants to initialize a connection it needs to specify the server's address and the port/socket to communicate on.
However, on the Server's side of things it only needs to know the port/socket to listen for requests on.

***

## Establishing a Connection

<details>
<summary>Server Connection steps</summary>

To Open a server up to start listening to request the following steps must be followed.

1. We must specify the **port** to listen on.
2. Initialize a ```ServerSocket``` and a ```Socket``` object assigning the port number to the ServerSocket and then start to accept connections into the socket.
3. Create a ```DataInputStream``` for incoming request s and a ```DataOutputStream``` for sending the data back to the client.
4. Close All Data Streams and Sockets.

```java
short port = 6060; // initialize the port

ServerSocket server = new ServerSocket(port); // initialized a SocketServer and assigned a port number
Socket socket = server.accept(); //Started to accept Connections

DataInputStream in = new DataInputStream(socket.getInputStream());  ///incoming traffic stream
DataOutputStream out = new DataOutputStream(socket.getOutputStream());   //data that would get sent back to the client.

server.close();
socket.close()
in.close();
out.close();
///Remember to close all streams and sockets.

```


</details>
<details>
<summary>Client Connection steps</summary>

To Initialize a Client to connect to a server and start sending requests we must do similar steps to starting a server.
1. Specify **port** number AND **IP address**.
2. Initialize a Socket and assign IP addr and socket number (This would also send a connection request to the server).
3. Initialize the data input and output streams ```DataInputStream``` and ```DataOutputStream``` to send and receive data to/from the server.
4. Close all sockets, datastreams, etc..

```java 
short port = 6060;
String host = "127.0.0.1"; ///Localhost 
Socket socket = new Socket(host, port); ///This function also sends a connection request to the server.    
DataInputStream in = new DataInputStream(socket.getInputStream());
DataOutputStream out = new DataOutputStream(socket.getOutputStream());

out.writeDouble(/*Value To Send to host*/);
double value = in.readDouble(); ////this can be used to output, store or update a value

```

</details>

***

## Client Address

If the requirement that a client needs to send it's IP Address to the server. This Could be achieved by creating an Object of of the InetAddress class and using the ```.getInetAddress();``` method then storing the value in a string by using the ```.getHostAddress();```

Example:
```java
InetAddress inetAddress = s.getInetAddress(); // 's' Being the Socket
String IP = inetAddress.getHostAddress();
```

***

