## AWS Networking Services 

- AWS provides a range of networking services to connect, secure, and manage cloud resources efficiently. Some of the key ones are:

**VPC (Virtual Private Cloud):** Lets you create your own private network in the cloud, like having a private office in a huge building.

**Route 53:** AWS’s DNS service, which helps translate domain names into IP addresses and route traffic globally.

**Direct Connect:** Provides a dedicated, private connection between your on-premises data center and AWS for faster and more secure traffic.

**Elastic Load Balancing (ELB):** Distributes incoming traffic across multiple servers so applications stay fast and available.

**CloudFront:** AWS’s Content Delivery Network (CDN), which caches content closer to users for faster website performance.

**VPN (Virtual Private Network):** Lets you securely connect your on-premises network to AWS over the internet.

**Transit Gateway:** Simplifies connecting multiple VPCs and on-premises networks through a single hub.

<img width="1447" height="671" alt="image" src="https://github.com/user-attachments/assets/ee507829-e16f-4549-9d88-3ec58a0759c5" />

-------------------

## AWS Enterprise / Hybrid Networking Services

Imagine your company has its own servers and office network, but you also want to use AWS cloud for apps, storage, or backups. You need a way to connect your office and cloud safely and smoothly. That’s what AWS Enterprise / Hybrid Networking does—it’s like building bridges between your office and AWS.

Here’s how it works in simple terms:

Direct Connect: Think of it as a private fast highway to AWS. No internet traffic, just your company data moving super fast and securely.

VPN: This is a secure tunnel over the internet. Good for connecting offices or letting remote workers access AWS safely.

Transit Gateway: Imagine a hub where all your networks meet. Instead of connecting each office separately, everything connects to this one hub.

VPC Peering: It’s like linking two cloud networks directly so they can talk to each other fast and privately.

PrivateLink: A private doorway to access AWS services or partner apps without going over the public internet.

Global Accelerator: If your users are everywhere in the world, this makes your apps faster by using AWS’s global network.

<img width="1532" height="752" alt="image" src="https://github.com/user-attachments/assets/549f6683-c1ee-4c77-975f-89c6f7565cf3" />

------------------------------------

## AWS VPC & Subnets

- A VPC, or Virtual Private Cloud, is basically your own private network inside AWS. Think of it as your company’s own office in the cloud. You can control the IP addresses, security rules, and who can access your resources. It’s isolated, so no one else’s traffic mixes with yours.

Inside a VPC, we create subnets, which are like rooms in that office. We usually have public subnets and private subnets. Public subnets are for resources that need internet access, like web servers, while private subnets are for secure resources like databases that shouldn’t be directly accessible from the internet. Subnets help us organize our network, control access, and make it more efficient.

We also use route tables, internet gateways, and security groups to control traffic between subnets and to/from the internet. For example, a web server in a public subnet can talk to a database in a private subnet securely within the same VPC, but the database isn’t exposed to the outside world.

So basically, VPC is your private network in AWS, subnets divide it logically, and security components control traffic and access.

---------------------------

## AWS Security Groups vs NACL

- "This diagram shows how traffic is controlled in a VPC using NACLs and Security Groups."

VPC (Virtual Private Cloud)

Think of the VPC as your private network in AWS. All your resources like EC2 instances live inside it.

Subnets

Subnets are like sections or rooms inside your VPC.

Here we have Subnet A and Subnet B, each containing multiple EC2 instances.

NACLs (Network Access Control Lists)

NACLs act as a firewall at the subnet level.

They control all traffic coming in and going out of the subnet.

You can allow or deny traffic based on IPs or protocols.

They are stateless, meaning if you allow incoming traffic, you also need to allow outgoing traffic.

In the diagram, NACL Subnet A controls traffic for Subnet A, and NACL Subnet B controls Subnet B.

Security Groups

Security Groups act as a firewall at the instance level.

They control traffic for each individual EC2 instance.

Security Groups are stateful, so responses to allowed traffic are automatically permitted.

You can only allow traffic; you cannot explicitly deny traffic here.

<img width="1541" height="752" alt="Screenshot 2025-12-22 133733" src="https://github.com/user-attachments/assets/16442f0f-7aca-4419-9d70-1207fb99a889" />

--------------------------

## AWS VPC Reserved Addresses

- When you create a VPC subnet in AWS, AWS automatically reserves 5 IP addresses in each subnet. These IPs are not available for your instances because they are used internally for networking purposes.

Think of your subnet like a street in a neighborhood, where each house is an IP address. AWS keeps a few houses reserved for important things:

Reserved IPs

First IP (Network address) – identifies the subnet itself

Second IP (VPC router / gateway) – the default gateway for the subnet

Third IP (AWS DNS) – used by AWS-provided DNS

Fourth IP (Future use) – reserved by AWS for future networking purposes

Last IP (Broadcast address) – marks the end of the subnet

----------------------

## Azure Virtual Network(vNet) & Subnets

- An Azure Virtual Network (vNet) is simply your own private network inside Azure, just like a company’s internal office network. It gives your Azure resources such as virtual machines, databases, and applications a safe space where they can communicate with each other using private IP addresses. You decide the IP range for the vNet, and Azure makes sure everything inside it stays isolated and secure from the outside world unless you allow access.

Inside a vNet, you create subnets, which are smaller sections of the network used to organize resources. You can think of subnets like different departments or blocks inside a building—each department has its own space but still belongs to the same building. For example, web servers can be placed in one subnet, application servers in another, and databases in a separate subnet. This separation helps in managing traffic, applying security rules, and keeping sensitive resources protected.

Azure also reserves a few IP addresses in every subnet for its own use, such as for the network itself, the gateway, and internal services. Because of this, not all IPs in a subnet are available for your virtual machines. Overall, vNet provides the private network, and subnets help divide and manage that network in a clean, secure, and organized way, making it easier to scale and control your Azure infrastructure.

----------------------

## Azure Networking Services (Azure DNS, Azure (vNET), Azure Load Balancer, Azure Application Gateway, Network Security Groups)

- Azure Networking Services are the tools Azure gives us to connect, manage, secure, and control traffic between applications and users. You can think of them as everything that helps data enter, move inside, and leave your Azure environment safely.

**Azure Virtual Network (vNet)** is the foundation of Azure networking. It is your private network in the cloud, where all your resources live and communicate using private IP addresses. Just like an office network, everything inside a vNet can talk to each other securely, and you control who can come in or go out.

**Azure DNS** works like the internet’s phonebook. Instead of remembering IP addresses, users access applications using easy names like myapp.com. Azure DNS translates these names into IP addresses so traffic reaches the correct resource. It is fast, reliable, and fully managed by Azure.

**Azure Load Balancer** helps when you have multiple servers running the same application. Instead of sending all traffic to one server, it distributes incoming traffic across healthy servers so the application stays fast and available, even if one server goes down.

**Azure Application Gateway** is similar to a load balancer but smarter. It understands web traffic (HTTP/HTTPS) and can make decisions based on URLs, host names, or paths. It also provides built-in security features like Web Application Firewall (WAF) to protect applications from common web attacks.

**Network Security Groups (NSGs)** act like security guards for your network. They control traffic by allowing or blocking connections based on rules such as source IP, destination IP, port number, and protocol. NSGs can be applied to subnets or individual network interfaces to control who can talk to what.

-----------------------------------

## Azure Enterprise /  Hybrid Networking Services

<img width="1461" height="708" alt="image" src="https://github.com/user-attachments/assets/4291d968-9f07-410b-b46d-9da8abe6d1c6" />

- This diagram is showing important Azure networking services that help with traffic entry, connectivity, and network management.

**Azure Front Door** is like the main entrance gate for your global application. When users from different countries access your app, Azure Front Door directs them to the nearest and fastest location. It also helps with security and performance, so users get a quick and safe experience.

**Azure ExpressRoute** is a private, dedicated connection between your on-premises data center and Azure. Unlike the internet, this connection is more secure, faster, and stable. It’s mainly used by large organizations that need reliable, high-speed connectivity.

**Virtual WAN (vWAN)** is used when a company has many branch offices or networks. Instead of managing everything separately, Virtual WAN brings VPNs, routing, and security together in one centralized place, making network management easier.

**Azure Connection (VPN Connection)** refers to a secure VPN tunnel that connects two Azure networks or an Azure network to on-premises using IPsec encryption. This ensures data travels securely over the internet.

**Virtual Network Gateway** acts like a bridge or door between your Azure VNet and another network (on-premises or another VNet). It enables Site-to-Site VPNs, allowing your local office network to communicate securely with Azure.

-----------------------------------------

## Network Security Group

- A Network Security Group is like a watchman or security guard for your Azure network. It checks all the traffic that is trying to enter or leave your resources and decides yes or no.

Whenever someone (traffic) wants to reach your VM or leave it, the NSG looks at a set of rules:

Where is it coming from?

Where is it going?

Which port is it using?

Is it allowed or blocked?

You can attach an NSG to a subnet (so everything inside follows the same rules) or directly to a VM’s network card (for more control).

**How NSG Rules Work -**

**Inbound rules** → control incoming traffic

**Outbound rules** → control outgoing traffic

Rules have priority numbers (smaller number = checked first)

If no rule matches, Azure blocks the traffic by default

------------------------

## Google Cloud Networking

<img width="742" height="577" alt="image" src="https://github.com/user-attachments/assets/f5087780-dd82-4c1b-bb83-ef24a81be6d4" />

- This diagram shows how a cloud network is set up with public and private subnets and how traffic flows in and out.

At the center, you have a VPC (Virtual Private Cloud). You can think of this as your own private network in the cloud. Everything inside it belongs to you. It’s created in a specific region, here shown as us-west-1.

Inside the VPC, there are two subnets:

The public subnet is for resources that need to be reachable from the internet. The server placed here has an external (public) IP address, so users from the cloud or internet can directly access it. Typical examples are web servers or load balancers.

The private subnet is for internal resources like application servers or databases. These servers do not have public IPs, so they cannot be accessed directly from the internet. This keeps them more secure.

When a server in the private subnet needs to go out to the internet (for updates or downloads), it uses Cloud NAT. Cloud NAT allows outbound internet access without exposing the server to incoming internet traffic.

On the right side, you see Firewall Rules. These act like security checks that decide which traffic is allowed or blocked between subnets, the internet, and on-premise networks.

At the bottom, you see On-Premise (your office or data center). This is connected to the VPC using Cloud VPN or Cloud Interconnect.

Cloud VPN is a secure connection over the internet.

Cloud Interconnect is a private, high-speed connection.

This allows your on-premise network to talk securely with resources inside the private subnet.

#### Cloud Armor, Cloud Load Balancing, Cloud CDN, Cloud NAT, Cloud DNS, Traffic Director, Cloud Interconnect, Coud Router

Cloud Armor

Cloud Armor protects your applications from attacks like DDoS and bad traffic.
Think of it as a security guard at the gate that blocks suspicious users before they reach your app.

Cloud Load Balancing

Cloud Load Balancing spreads traffic across multiple servers so no single server gets overloaded.
It keeps your application fast and available, even if one server goes down.

Cloud CDN

Cloud CDN stores copies of your content closer to users around the world.
This means faster loading websites and less load on your main servers.

Cloud NAT

Cloud NAT allows private servers to access the internet without having public IPs.
Your servers can go out safely, but outsiders can’t directly reach them.

Cloud DNS

Cloud DNS translates website names into IP addresses so users reach the correct server.
It’s like the internet’s contact list, fast and reliable.

Traffic Director

Traffic Director decides where traffic should go based on rules and health checks.
It helps services talk to the best available backend without delays.

Cloud Interconnect

Cloud Interconnect provides a private, high-speed connection between your on-premises network and the cloud.
It’s more stable and secure than using the public internet.

Cloud Router

Cloud Router manages how traffic moves between your cloud network and on-premises.
It automatically shares routes so both sides know how to reach each other.

-----------------------

