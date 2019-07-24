### AWS - Getting Started

[Best Place to start AWS](https://aws.amazon.com/getting-started/)

### Global Infrastructure

#### Why Cloud Infrastructure Matters

Companies around the world are moving to a cloud-based infrastructure to increase IT agility, gain unlimited scalability, improve reliability, and lower costs. They want the flexibility to expand their operations at a rapid pace without worrying about setting up new IT infrastructure. They want to enhance their end-user and customer experiences by minimizing latency, the time it takes for their data packets to travel, so they can avoid delays and interruptions. As well, customers want to be able to easily support any country-specific data sovereignty requirements, which means they need the flexibility to have a wide selection of geographic regions of data centers from which to choose to deploy their application workloads.
The AWS global infrastructure delivers a cloud infrastructure companies can depend on—no matter their size, changing needs, or challenges. The AWS Global Infrastructure is designed and built to deliver the most flexible, reliable, scalable, and secure cloud computing environment with the highest quality global network performance available today. Every component of the AWS infrastructure is design and built for redundancy and reliability, from regions to networking links to load balancers to routers and firmware. 


### Data Center

A data center (or datacenter) is a facility composed of networked computers and storage that businesses or other organizations use to organize, process, store and disseminate large amounts of data. A business typically relies heavily upon the applications, services and data contained within a data center, making it a focal point and critical asset for everyday operations


### Cloud computing

Cloud computing is the on-demand availability of computer system resources, especially data storage and computing power, without direct active management by the user. The term is generally used to describe data centers available to many users over the Internet. Large clouds, predominant today, often have functions distributed over multiple locations from central servers. If the connection to the user is relatively close, it may be designated an edge server.


### Virtualization in Cloud Computing

Virtualization is the "creation of a virtual (rather than actual) version of something, such as a server, a desktop, a storage device, an operating system or network resources".

In other words, Virtualization is a technique, which allows to share a single physical instance of a resource or an application among multiple customers and organizations. It does by assigning a logical name to a physical storage and providing a pointer to that physical resource when demanded.

### Docker

Docker is an open source software platform to create, deploy and manage virtualized application containers on a common operating system (OS), with an ecosystem of allied tools. Docker Inc., the company that originally developed Docker, supports a commercial edition and is the principal sponsor of the open source tool.

Docker is a tool that packages, provisions and runs containers independent of the OS. Container technology is available through the operating system: A container packages the application service or function with all of the libraries, configuration files, dependencies and other necessary parts to operate. Each container shares the services of one underlying operating system.

Docker was created to work on the Linux platform, but has extended to offer greater support for non-Linux operating systems, including Microsoft Windows and Apple OS X. Versions of Docker for Amazon Web Services (AWS) and Microsoft Azure are available.

#### Docker advantages and disadvantages

Docker has emerged as a de facto standard platform that allows users to quickly compose, create, deploy, scale and oversee containers across Docker hosts. Docker allows a high degree of portability so that users can register and share containers over various hosts in private and public environments. Docker benefits include efficient application development, lower resource use and faster deployment compared to VMs.

There are also potential challenges with Docker. The sheer number of containers possible in an enterprise can be difficult to manage efficiently. Security can also pose a problem. Despite excellent logical isolation, containers share the host's operating system. An attack or flaw in the underlying operating system can potentially compromise all of the containers running atop the OS. Some organizations run containers within a VM, although containers do not require virtual machines.


### Kubernates

Kubernetes is a popular open source platform for container orchestration — that is, for the management of applications built out of multiple, largely self-contained runtimes called containers. Containers have become increasingly popular since the Docker containerization project launched in 2013, but large, distributed containerized applications can become increasingly difficult to coordinate. By making containerized applications dramatically easier to manage at scale, Kubernetes has become a key part of the container revolution.

#### What is container orchestration?

Containers support VM-like separation of concerns but with far less overhead and far greater flexibility. As a result, containers have reshaped the way people think about developing, deploying, and maintaining software. In a containerized architecture, the different services that constitute an application are packaged into separate containers and deployed across a cluster of physical or virtual machines. But this gives rise to the need for container orchestration—a tool that automates the deployment, management, scaling, networking, and availability of container-based applications.

#### What is Kubernetes?

Kubernetes is an open source project that has become one of the most popular container orchestration tools around; it allows you to deploy and manage multi-container applications at scale. While in practice Kubernetes is most often used with Docker, the most popular containerization platform, it can also work with any container system that conforms to the Open Container Initiative (OCI) standards for container image formats and runtimes. And because Kubernetes is open source, with relatively few restrictions on how it can be used, it can be used freely by anyone who wants to run containers, most anywhere they want to run them—on-premises, in the public cloud, or both.

#### Google and Kubernetes
Kubernetes began life as a project within Google. It’s a successor to—though not a direct descendent of—Google Borg, an earlier container management tool that Google used internally. Google open sourced Kubernetes in 2014, in part because the distributed microservices architectures that Kubernetes facilitates makes it easy to run applications in the cloud. Google sees the adoption of containers, microservices, and Kubernetes as potentially driving customers to its cloud services (although Kubernetes certainly works with Azure and AWS as well). Kubernetes is currently maintained by the Cloud Native Computing Foundation, which is itself under the umbrella of the Linux Foundation.


#### Kubernetes architecture: How Kubernetes works

Kubernetes’s architecture makes use of various concepts and abstractions. Some of these are variations on existing, familiar notions, but others are specific to Kubernetes.

##### Kubernetes clusters

The highest-level Kubernetes abstraction, the cluster, refers to the group of machines running Kubernetes (itself a clustered application) and the containers managed by it. A Kubernetes cluster must have a master, the system that commands and controls all the other Kubernetes machines in the cluster. A highly available Kubernetes cluster replicates the master’s facilities across multiple machines. But only one master at a time runs the job scheduler and controller-manager.

##### Kubernetes nodes and pods

Each cluster contains Kubernetes nodes. Nodes might be physical machines or VMs. Again, the idea is abstraction: Whatever the app is running on, Kubernetes handles deployment on that substrate. Kubernetes even makes it possible to ensure that certain containers run only on VMs or only on bare metal.

Nodes run pods, the most basic Kubernetes objects that can be created or managed. Each pod represents a single instance of an application or running process in Kubernetes, and consists of one or more containers. Kubernetes starts, stops, and replicates all containers in a pod as a group. Pods keep the user’s attention on the application, rather than on the containers themselves. Details about how Kubernetes needs to be configured, from the state of pods on up, is kept in Etcd, a distributed key-value store.

Pods are created and destroyed on nodes as needed to conform to the desired state specified by the user in the pod definition. Kubernetes provides an abstraction called a controller for dealing with the logistics of how pods are spun up, rolled out, and spun down. Controllers come in a few different flavors depending on the kind of application being managed. For instance, the recently introduced “StatefulSet” controller is used to deal with applications that need persistent state. Another kind of controller, the deployment, is used to scale an app up or down, update an app to a new version, or roll back an app to a known-good version if there’s a problem.

##### Kubernetes services

Because pods live and die as needed, we need a different abstraction for dealing with the application lifecycle. An application is supposed to be a persistent entity, even when the pods running the containers that comprise the application aren’t themselves persistent. To that end, Kubernetes provides an abstraction called a service.

A service in Kubernetes describes how a given group of pods (or other Kubernetes objects) can be accessed via the network. As the Kubernetes documentation puts it, the pods that constitute the back-end of an application might change, but the front-end shouldn’t have to know about that or track it. Services make this possible.

A few more pieces internal to Kubernetes round out the picture. The scheduler parcels out workloads to nodes so that they’re balanced across resources and so that deployments meet the requirements of the application definitions. The controller manager ensures that the state of the system—applications, workloads, etc.—matches the desired state defined in Etcd’s configuration settings.

It is important to keep in mind that none of the low-level mechanisms used by containers, such as Docker itself, are replaced by Kubernetes. Rather, Kubernetes provides a larger set of abstractions for using these mechanisms for the sake of keeping apps running at scale.

##### Kubernetes Ingress

Kubernetes services are thought of as running within a cluster. But you’ll want to be able to access these services from the outside world. Kubernetes has several components that facilitate this with varying degrees of simplicity and robustness, including NodePort and LoadBalancer, but the component with the most flexibility is Ingress. Ingress is an API that manages external access to a cluster’s services, typically via HTTP.


### The Symbiosis Between Kubernetes and Docker

The question, “Kubernetes or Docker?” in itself is rather absurd, like comparing apples to oranges. One isn’t an alternative to the other. Quite the contrary; Kubernetes can run without Docker and Docker can function without Kubernetes. But Kubernetes can (and does) benefit greatly from Docker and vice versa.

Docker is a standalone software that can be installed on any computer to run containerized applications. Containerization is an approach of running applications on an OS such that the application is isolated from the rest of the system. You create an illusion for your application that it is getting its very own OS instance, although there may be other containers running on same system. Docker is what enables us to run, create and manage containers on a single operating system.

Kubernetes turns it up to 11, so to speak. If you have Docker installed on a bunch of hosts (different operating systems), you can leverage Kubernetes. These nodes, or Docker hosts, can be bare-metal servers or virtual machines. Kubernetes can then allow you to automate container provisioning, networking, load-balancing, security and scaling across all these nodes from a single command line or dashboard. A collection of nodes that is managed by a single Kubernetes instance is referred to as a Kubernetes cluster.

Now, why would you need to have multiple nodes in the first place? The two main motivations behind it are:

To make the infrastructure more robust: Your application will be online, even if some of the nodes go offline, i.e, High availability.
To make your application more scalable: If workload increases, simply spawn more containers and/or add more nodes to your Kubernetes cluster.
Kubernetes automates the process of scaling, managing, updating and removing containers. In other words, it is a container orchestration platform. While Docker is at the heart of the containerization, it enables us to have containers in the first place.

### Differences Between Kubernetes and Docker

In principle, Kubernetes can work with any containerization technology. Two of the most popular options that Kubernetes can integrate with are rkt and Docker. However, Docker has the most mindshare, which has led to much more effort in perfecting the integration between it and Kubernetes more than any other containerization technology.

Similarly, Docker Inc., the company behind Docker, offers its own container orchestration engine, Docker Swarm. But even the company realized the fact that Kubernetes has risen to the point that even Docker for Desktop (MacOS and Windows) comes with its own Kubernetes distribution.

If anyone was nervous about adopting Kubernetes for their Docker-based product, that last point should relieve any doubts. Both projects have wholeheartedly embraced each other and have benefited tremendously from this symbiosis.


### Multi-factor Authentication(MFA)

AWS Multi-Factor Authentication (MFA) is a simple best practice that adds an extra layer of protection on top of your user name and password. With MFA enabled, when a user signs in to an AWS website, they will be prompted for their user name and password (the first factor—what they know), as well as for an authentication code from their AWS MFA device (the second factor—what they have). Taken together, these multiple factors provide increased security for your AWS account settings and resources.

You can enable MFA for your AWS account and for individual IAM users you have created under your account. MFA can be also be used to control access to AWS service APIs.

After you've obtained a supported hardware or virtual MFA device, AWS does not charge any additional fees for using MFA.

You can also protect cross-account access using MFA.


### VPC (Virtual Private Cloud)

#### Q. What is Amazon Virtual Private Cloud?

Amazon VPC lets you provision a logically isolated section of the Amazon Web Services (AWS) cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address ranges, creation of subnets, and configuration of route tables and network gateways. You can also create a hardware Virtual Private Network (VPN) connection between your corporate datacenter and your VPC and leverage the AWS cloud as an extension of your corporate datacenter.

You can easily customize the network configuration for your Amazon VPC. For example, you can create a public-facing subnet for your web servers that have access to the Internet, and place your backend systems such as databases or application servers in a private-facing subnet with no Internet access. You can leverage multiple layers of security, including security groups and network access control lists, to help control access to Amazon EC2 instances in each subnet.

#### Q. What are the components of Amazon VPC?

Amazon VPC comprises a variety of objects that will be familiar to customers with existing networks:

A Virtual Private Cloud: A logically isolated virtual network in the AWS cloud. You define a VPC’s IP address space from ranges you select.

Subnet: A segment of a VPC’s IP address range where you can place groups of isolated resources.

Internet Gateway: The Amazon VPC side of a connection to the public Internet.

NAT Gateway: A highly available, managed Network Address Translation (NAT) service for your resources in a private subnet to access the Internet.

Virtual private gateway: The Amazon VPC side of a VPN connection.

Peering Connection: A peering connection enables you to route traffic via private IP addresses between two peered VPCs.

VPC Endpoints: Enables private connectivity to services hosted in AWS, from within your VPC without using an Internet Gateway, VPN, Network Address Translation (NAT) devices, or firewall proxies.

Egress-only Internet Gateway: A stateful gateway to provide egress only access for IPv6 traffic from the VPC to the Internet.

#### Q: Why should I use Amazon VPC?
 
Amazon VPC enables you to build a virtual network in the AWS cloud - no VPNs, hardware, or physical datacenters required. You can define your own network space, and control how your network and the Amazon EC2 resources inside your network are exposed to the Internet. You can also leverage the enhanced security options in Amazon VPC to provide more granular access to and from the Amazon EC2 instances in your virtual network.

#### What is the relation between an AWS VPC subnet and a route table?

VPCs - A VPC is a logical boundary within AWS’ public cloud - one that provides YOU private access. How many VPCs you need is dictated by the number of environments - for e.g. Your may want a PROD VPC for all your production instances and a STAGING VPC for your staging environment.. Of course, there are many other ways to do your VPC layout, this is a just a common example. Sometimes, a ‘Management’ VPC that contains all the bastion hosts etc. is added - and all your other VPCs (Prod, Staging) are peered with the management VPC. Typically, VPCs cannot talk to each other unless they have been ‘peered’.

Subnets - Whereas VPC layout is based on environment, Subnets are usually dictated by the type of workload. In a standard 3 tier app, your web tier would be in its own subnet (called WEB), your app would be in another Subnet (called APP) and your data would sit in the DATA subnet. These subnets are defined by YOU , the admin account owner of the AWS dashboard. How many IP addresses and what block (CIDR block) you provide per subnet is also something you get to decide (e.g. /16 subnet gets you 65536 IP addresses and /28 gets you 16 IPs).

You HAVE to get this right upfront - no way to add or remove IP addresses once a subnet is created

A subnet can be either Public or private.. The only difference is that a public subnet has an internet gateway associated with it. A private one does not - and needs a NAT instance to get out to the internet.

In our workload example above, you would want your WEB subnet to be a PUBLIC subnet and your APP and DATA subnets to be private.

Route Tables - If you stick to default VPCs and default Subnets, you already have routes from each instance in the subnet to a) Other instances in the same subnet b) to the internet (for a Public Subnet).

It is only when you move away from default VPCs - and create your own VPC that you really need to start thinking about routes. In that case, you would need to create a route for each EC2 instance (in public subnet) to get out to the internet. You would only do this ONCE - by creating a ROUTE TABLE - and assigning each EC2 instance to this route table.

You can, obviously create more convoluted routes, for e.g. - from a Private EC2 instance in APP subnet to a private EC2 instance in the DATA subnet.

##### To put it simple:

Each VPC has a main route table. There is a default one, which can be modified or replaced with a custom route table.

Each subnet must be associated with a route table. It can be an explicitly specified custom route table, or if you don’t do that, the subnet uses the VPC’s main route table.

Route table controls the subnet’s traffic. AWS has 3 types of subnets:

Public subnet: the route table directs traffic to IGW (Internet Gateway) for Internet access.

Private subnet: the router table does not direct traffic to IGW and therefore no Internet access.

VPN-only subnet: the route table directs traffic to VPG (VPN Gateway) for VPN access, but not to IGW.


### Before 
starting with the VPC subnet we must first know what is a VPC. VPC is a virtual private network provided by the AWS to create your network to isolate your resources from others. VPC is a region specific services. Your network would be identified with the help of the IP address.

VPC subnet is the component which divides the network into smaller networks that is it divides the IP address into small portion to use it in its availability zones.

There are two types of subnet namely private and public subnets.

The public subnets are the subnets which face the internet, that is the resources like your application is placed inside this subnet.

The private subnets are the subnets which are not reachable through the internet, that is more secure resources are placed on this subnet such as database, backups, etc.

Route Table is the VPC component which helps to classify the subnet as private or public by specifying the traffic that has to be directed to each subnet.

Route table does it by specifying the destination IP address in it and the target that has to be reached if the traffic arises for the destination address.

Each subnet has to be attached with at least one route table but a Route table can be attached with any no of subnets.

### IMP Links

[AWS Free Account Fearures](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc)


### Screenshots

![VPC 1](./Screenshots/VPC1.png?raw=true "Optional Title")

![VPC 2](./Screenshots/VPC2.png?raw=true "Optional Title")
