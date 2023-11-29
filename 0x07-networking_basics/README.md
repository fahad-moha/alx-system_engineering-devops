# Networking Fundamentals

## OSI Model
The OSI (Open Systems Interconnection) model is a conceptual framework that standardizes the functions of a communication system into seven distinct layers. Each layer has specific responsibilities and interacts with adjacent layers to facilitate data communication.

- The OSI model consists of seven layers.
- The layers are organized in a hierarchical manner, with each layer providing services to the layer above it and utilizing services from the layer below it.
- The seven layers, from bottom to top, are: Physical, Data Link, Network, Transport, Session, Presentation, and Application.

## LAN (Local Area Network)
A LAN refers to a computer network that covers a small geographic area, typically within a single building or campus.

- LANs are commonly used in homes, offices, schools, and small organizations.
- They facilitate local data sharing, resource sharing, and communication between devices within the network.
- Geographical size: Typically covers a small area, such as a building or campus.

## WAN (Wide Area Network)
A WAN is a computer network that spans a large geographic area and connects multiple LANs or other networks together.

- WANs are used to connect geographically dispersed locations, such as different offices or cities.
- They enable long-distance communication and data transfer between connected networks.
- Geographical size: Can span across cities, countries, or even continents.

## Internet
The Internet is a global network of interconnected networks that allows communication and information exchange on a global scale.

- It is a vast network infrastructure that connects billions of devices worldwide.
- The Internet enables access to various services, such as email, web browsing, online gaming, and file sharing.
- It uses the IP (Internet Protocol) as its underlying communication protocol.

## IP Address
An IP address is a unique numeric identifier assigned to each device on a network that uses the Internet Protocol for communication.

- It serves as the address of a device and allows it to send and receive data over an IP-based network.
- IPv4 (Internet Protocol version 4) and IPv6 (Internet Protocol version 6) are the two types of IP addresses.

## IPv4 and IPv6
- IPv4: It is a 32-bit address written in the form of four sets of numbers separated by periods (e.g., 192.168.0.1). It has a limited address space and is being gradually replaced by IPv6.
- IPv6: It is a 128-bit address written in the form of eight sets of numbers separated by colons (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334). It provides a significantly larger address space to accommodate the growing number of devices connected to the Internet.

## localhost
"localhost" refers to the loopback network interface of a device, typically represented by the IP address 127.0.0.1.

- It is used to access the network services running on the same device.
- When a program or service is configured to listen on the localhost address, it can be accessed only from the local machine.

## Subnet
A subnet is a logical subdivision of an IP network. It allows for the division of a large network into smaller, more manageable segments.

- Subnetting helps in efficient network management, security, and improved performance.
- It involves dividing the IP address space into smaller network addresses using subnet masks.

## IPv6 Creation
IPv6 was created due to the limitations of IPv4, primarily the exhaustion of available IPv4 addresses.

- With the rapid growth of the Internet and the increasing number of connected devices, the larger address space provided by IPv6 was necessary to meet the demand for unique IP addresses.

## TCP/UDP
TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are two commonly used transport layer protocols in the OSI model.

- TCP provides reliable, connection-oriented data transfer with error detection and retransmission mechanisms.
- UDP provides unreliable, connectionless data transfer without error detection or retransmission. It is often used for real-time communication and streaming applications.

## Difference between TCP and UDP
The main difference between TCP and UDP is the level of reliability and the features they offer:

- TCP guarantees reliable data delivery through error detection, retransmission of lost packets, and in-order delivery.
- UDP offers faster, connectionless data transfer without the overhead of reliability mechanisms, making it suitable for real-time applications where speed is crucial.

## Port
A port is a communication endpoint in an operating system that is uniquely identified by a number.

- Ports allow multiple applications or services to utilize network resources simultaneously.
- They are identified by port numbers, which are divided into three ranges: well-known ports (0-1023), registered ports (1024-49151), and dynamic or private ports (49152-65535).

## SSH, HTTP, and HTTPS Port Numbers
- SSH (Secure Shell): Port 22
- HTTP (Hypertext Transfer Protocol): Port 80- HTTPS (Hypertext Transfer Protocol Secure): Port 443

## Device Network Connectivity Checking
A common tool/protocol used to check if a device is connected to a network is the ICMP (Internet Control Message Protocol) echo request/reply mechanism, commonly known as "ping."

- The ping command sends an ICMP echo request packet to the target device and waits for an ICMP echo reply packet.
- If a reply is received, it indicates that the device is connected and responsive on the network.
