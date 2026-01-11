## What is a Network?

- **A network is simply when two or more devices are connected so they can talk to each other and share information.** we use networks all the time without thinking about it. For example, when I connect my mobile or laptop to Wi-Fi and open the internet, that connection is a network. The devices send data to each other to make things work.

So basically, a network helps devices share things like internet access, files, or printers and makes communication fast and easy.

----------------------------------

## What is a Subnet?

- **A subnet is basically a smaller part of a bigger network.**
that means instead of keeping all devices in one large network, we divide it into smaller networks called subnets. This makes the network easier to manage and reduces unnecessary traffic.

**For example**, in an office, different departments like HR, Finance, and IT can be put into different subnets. Even though they are part of the same main network, each subnet works separately, which improves performance and security.

----------------------------------------

## What is vLAN?

- A VLAN (Virtual LAN) is used to divide one physical network into multiple separate logical networks.

Even if all devices are connected to the same switch, VLANs allow us to group them separately based on requirement.

Example:
In a company:

**HR VLAN**– All HR department systems are placed in one VLAN

**IT VLAN** – IT team systems are placed in a different VLAN

**Sales VLAN** – Sales team systems are placed in another VLAN

Although all employees may be using the same network switch, HR, IT, and Sales work in separate VLANs. They cannot communicate with each other unless inter-VLAN routing is configured. This improves network security, reduces unnecessary traffic, and makes network management easier.

---------------------------

## Switching & Routing (Route Table)

- **Switching and Routing are two core networking concepts used to move data from one place to another.**

**Switching** works inside the same network. A switch forwards data between devices in the same LAN using **MAC addresses**. For example, when two computers are connected to the same switch, the switch sends data directly to the correct device without sending it to everyone.

**Routing** is used when data needs to go between different networks. A router decides the best path for the data using a **route table**.

**Route Table** is like a reference list inside the router. It contains network destinations and the next path (next hop) to reach them. When a packet arrives, the router checks the route table and forwards the packet to the correct network.

So, switching handles communication within a network, while routing and route tables handle communication between different networks.

<img width="1212" height="669" alt="image" src="https://github.com/user-attachments/assets/454124cd-259f-42b8-beaf-18df4eb8a3cb" />

------------------

## Ethernet Frame

Ethernet Frame is basically the format in which data is sent on a network at Layer 2 (Data Link layer).

When one device sends data to another over Ethernet, it doesn’t send raw data directly. It packs the data into a frame, just like putting a letter inside an envelope with proper details.

When communication starts, the Preamble is sent first.
This helps the receiving device get ready and synchronize itself. You can think of it as a “heads-up” signal saying data is coming.

After that comes the Start Frame Delimiter (SFD).
This clearly marks the actual start of the Ethernet frame.

Next is the Destination MAC Address.
This tells the switch or device who should receive this frame.

Then comes the Source MAC Address.
This identifies who sent the frame.

After that is the EtherType / Length field.
This tells what type of data is inside the frame, for example whether it’s an IPv4 packet, ARP, or something else.

Then comes the Data (Payload).
This is the actual information being sent, like an IP packet. This is the main content.

Finally, there is the Frame Check Sequence (FCS).
This is used for error checking. The receiver checks this value to make sure the data was not corrupted during transmission.

<img width="1452" height="742" alt="image" src="https://github.com/user-attachments/assets/7227e0ca-02d1-47de-8024-5d040ac7e5bf" />

-------------------------

## IP Address

- An IP address is a unique number given to a device on a network so it can be identified and communicated with.

Just like we need a home address to receive letters, devices need an IP address to send and receive data on a network or the internet. When I open a website, my device uses IP addresses to know where to send the request and where to get the response from.

For example, if two computers are connected to the same network, each one has a different IP address. This helps the network know which data belongs to which device. Without IP addresses, devices wouldn’t know where to send information.

----------------------

## Binary Math (0 or 1)

- Binary math is the basic language that computers use to understand and process data. Instead of numbers like 1, 2, 3, computers work only with **two values: 0 and 1**.

* **0** means OFF, NO signal, or FALSE
* **1** means ON, YES signal, or TRUE

You can think of it like a light switch:

* Switch OFF = 0
* Switch ON = 1

Every IP address, file, message, or command in a network is finally converted into 0s and 1s so the computer can understand it.

**Example:**
Binary number `101`

* 1 = ON
* 0 = OFF
* 1 = ON

So, binary math is just a simple way computers use ON and OFF signals to store and send information.

------------------

## POP (Point of Presence)

- **Point of Presence (PoP)** is basically a physical location where a network or internet service provider has equipment to connect users to the internet or their network.

In simple words, it’s like a **local office of the network** that helps people or businesses connect to the internet faster and more reliably.

**Example:**

* If you’re using an ISP, your internet traffic goes to the nearest PoP first before reaching the main network.
* Big companies like AWS, Google Cloud, and telecom operators have multiple PoPs around the world to provide faster access to their services.

It helps in **reducing delays**, **improving speed**, and **connecting users efficiently**.

-----------------

## Global Networks – Global Infra (Regions & Fault Tolerance)

- Global networks are basically the way companies set up their infrastructure across the world. Regions are like big areas or zones where the company has data centers. For example, there might be a region in India, another in the US, and one in Europe. The idea is to serve users from the nearest region so things are faster and smoother, and also to follow local rules about where data can be stored.

Fault tolerance is about making sure the system keeps running even if something goes wrong. If one data center or region fails, another one automatically takes over. This prevents downtime and ensures that users can keep using the service without noticing any issues. Companies achieve this by having backups, multiple regions, and systems that can automatically switch traffic in case of failure.

-----------------

## CIDR 

- CIDR is a way to write IP addresses more flexibly than the old class-based system. Instead of dividing networks strictly into Class A, B, or C, CIDR lets you specify how many bits are used for the network part. This helps in efficiently using IP addresses and reduces waste.

It is written like this: 192.168.1.0/24

The /24 means the first 24 bits are for the network and the rest are for hosts.

You can adjust it to create networks of different sizes depending on how many devices you need.

--------------

## Classfull Addressing

Classful addressing is the old way of dividing IP addresses into different buckets called classes – A, B, C, D, and E. Each class was meant for networks of different sizes.

Class A – for really big networks with lots of devices.

Class B – for medium-sized networks.

Class C – for small networks, like an office network.

Class D – used for sending data to multiple devices at once (multicast).

Class E – reserved for future use or experiments.

The problem was that it wasted a lot of IP addresses because the sizes were fixed. That’s why later we got CIDR, which is a smarter and flexible way to divide IPs.

-----------------------------

## Network Physical Media Types

- Network physical media is basically the physical way data travels in a network. It’s like the ‘road’ for data. There are a few main types:

Twisted Pair Cable (Copper Cable) – Most common, used in homes and offices (like Ethernet cables). It’s cheap and easy to use.

Coaxial Cable – Older type, used for cable TV and some internet connections. It has better shielding than twisted pair.

Fiber Optic Cable – Uses light to send data, so it’s very fast and can travel long distances without losing quality.

Wireless (Radio, Wi-Fi, Microwave) – No physical cables; data travels through air. Convenient but can be affected by distance and interference.

----

## Network Address Translation(NAT)

- NAT is a method used to translate private IP addresses of devices in a network to a public IP address so they can communicate with the internet.

Imagine all the devices in your home—laptop, phone, tablet—want to go online. Each one has its own private address, but the internet only knows public addresses. NAT works like a smart receptionist: it takes requests from your devices, swaps their private addresses with your router’s public IP, sends it to the internet, and then brings back the response to the right device.

Basically, NAT hides your private IPs, saves public IPs, and keeps your network a bit safer, all without you noticing anything.

<img width="957" height="596" alt="image" src="https://github.com/user-attachments/assets/2b2cedc2-c884-4fce-a172-c1d6f86f046b" />


---------------------------------

## DNS64 & NAT64

- DNS64:
“DNS64 is like a translator for addresses. If your device only understands IPv6 but wants to visit a website that only has an IPv4 address, DNS64 makes a special IPv6 version of that IPv4 address so your device can reach it. It’s like giving someone a phone number in a language they understand.”

NAT64:
“NAT64 works like a post office for your data. Your IPv6-only device sends a request, NAT64 converts it into IPv4, sends it to the server, then converts the response back to IPv6. This way, IPv6 devices can communicate with IPv4 servers without any problems.”

<img width="1096" height="742" alt="image" src="https://github.com/user-attachments/assets/6b5ab93a-1ae7-48a7-ac01-028ee9e7621d" />


---------------------------

## Gateway / Netfilter

- **Gateway:**
“A gateway is like a door or bridge between two networks. For example, your home Wi-Fi router acts as a gateway between your devices and the internet. It decides where the data should go, so your laptop can reach websites outside your local network.”

**Netfilter:**
“Netfilter is like a traffic police inside your network. It’s part of Linux that controls, filters, and manages network packets. It decides which packets are allowed, which are blocked, and can even change them if needed. Basically, it helps protect the network and manage traffic efficiently.”

-------------------

## Various Proxy / Load Balancing

- Proxy:
“A proxy is like a middleman between your device and the internet. When you make a request, it goes through the proxy first, which can filter, hide your IP, cache content, or improve security. For example, a company might use a proxy so employees can access the internet safely and anonymously.”

Load Balancing:
“Load balancing is like a traffic manager for servers. When lots of users try to access a website, the load balancer distributes requests across multiple servers so no single server gets overloaded. This keeps the website fast, reliable, and available all the time.”

-------------------

## In-Transit vs At-Rest encryption

- In-Transit Encryption:
“In-transit encryption is used to protect data while it is moving from one place to another, like between your computer and a website, or between two servers. Think of it as sending a letter in a sealed envelope—even if someone intercepts it while it’s on the way, they cannot read it. Common examples include HTTPS for websites, SSL/TLS for emails, and VPNs.”

At-Rest Encryption:
“At-rest encryption protects data when it is stored, such as on a hard drive, cloud storage, or database. It’s like locking your important documents in a safe. Even if someone steals the storage device or accesses the server, they cannot read the data without the encryption key. Examples include BitLocker, database encryption, and cloud storage encryption.”

Why both are important:

In-transit encryption ensures your data is safe while moving across networks.

At-rest encryption ensures your data is safe while sitting in storage.

Together, they provide end-to-end protection, keeping data secure both in motion and at rest.

-----------------------

## IPSec

- IPSec (Internet Protocol Security) is a technology that secures communication over the internet or any IP network. It makes sure that data sent between two devices or networks is private, safe, and authentic.

Imagine you want to send a secret letter to a friend across a busy street where anyone could peek at it. IPSec acts like a special armored tunnel for your letter:

Encryption – Your letter is locked in a way that only your friend can open it, so nobody else can read it.

Authentication – It makes sure your friend really receives it from you, and not from some stranger pretending to be you.

Data Integrity – It ensures the letter hasn’t been tampered with during the journey.

IPSec is widely used for VPNs, where employees connect securely to their company network from home or other remote locations. So basically, it’s a secure private tunnel over a public network, keeping your data safe from hackers and eavesdroppers.

-------------

## Protocol Data Units(PDU)

- PDU stands for Protocol Data Unit, and I usually think of it like a package of data that moves through the network. Depending on which layer of the OSI or TCP/IP model you’re at, the package has different information added.

For example:

At the Application layer, it’s just the actual data or message.

At the Transport layer, it becomes a segment with port info.

At the Network layer, it’s called a packet with source and destination addresses.

At the Data Link layer, it’s a frame with MAC addresses and error checking.

And at the Physical layer, it’s sent as raw bits over cables or air.

So basically, a PDU is how data is packaged and prepared at each layer so it can travel safely and reach the right device.

-----------------

## Remote Desktop Protocol (RDP)

- RDP, or Remote Desktop Protocol, is a technology that lets you control another computer over a network or the internet as if you were sitting right in front of it.

For example, if you’re at home and need to use your office computer, RDP lets you see the office desktop, run applications, and access files remotely. It’s like streaming the screen from the other computer while your keyboard and mouse control it.

RDP also encrypts the connection to keep the session secure, and it’s widely used by IT teams for remote support, troubleshooting, or remote work.

-----------------------

