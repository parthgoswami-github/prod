# How does VPC work?

<a href="/images/decoding_vpc/VPC_intro.png" target="_blank"><img src="/images/decoding_vpc/VPC_intro.png" width="200px" align="right" /></a>
<br/>
If you start from the bare metal layer and go right up until the container layer through virtualization, base OS and the container engine, you would notice that networking runs throughout the stack. 

Networking is the backbone of any infrastructure. Hence, understanding the networking concepts becomes very important and if we are talking about cloud computing, it becomes ever more important. 

In this article, I will be discussing how networking works in the cloud computing. For clarity, this article focuses on **Virtual Private Cloud[VPC]**, a networking service provided by *Amazon Web Services*.
 
Let's dive into it!

## What is VPC?
VPC stands for Virtual Private Cloud and is one of the most fundamental and widely used AWS service which provides a virtual network dedicated for the AWS environments. It is logically isolated from the other virtual networks in the cloud and exists within a single region. VPC allows for more control of AWS Cloud Network with extra layer of security.


## How does VPC works?

1. VPC cannot talk directly to the internet. For that we need **Internet Gateway** to talk to the internet. Internet Gateway is used to allow resources (subnets) in your VPC to access Internet.

2.  VPC can have multiple **subnets** and these subnets can be  public facing or private. Subnets are the the spaces where your applications are running. Subnets are been decided by **CIDR( Classless inter-domain routing)**.

3. Public subnets are the ones that are accessible to the internet and Private subnets are the ones that are not accessible by the internet. For example:  Amazon Shopping Website, you cannot access the database of this website but you can access the application of Amazon Shopping Website . This means that the application is running on public subnet and the database is running on private subnet.
 
4. We decide these public and private subnets using **Route Table**. Route table is the place where you put all the entries of these public and private subnets i.e. IP address.

5. Every VPC has one default Route table. All subnets that you launch will be a part of this Route table.

6. Everything will go into the Route table i.e. public subnet, private subnet and the internet gateway which means anyone who is coming can access my private subnet which is dangerous. To over come this we use different Route tables i.e. we will make different public route table and different private route table i.e. the internet gateway can access my public subnet and not the private subnet.

7. All the new entries of the subnet will enter into default Route table and whenever you want you can move these entries into public or private subnets.

8. Internet gateway can access the public subnet and public subnet will communicate with the private subnet.

9.  If the  private subnet wants to talk to the internet but it cannot communicate directly to the internet that time we will use **NAT**. NAT, *Network Address Translation*, refers to the proxy server. Private subnet will talk to the internet through NAT but internet will not talk directly to the private subnet, it will first communicate with public subnet and then public subnet will talk to the private subnet.

![](/images/decoding_vpc/VPC.png "VPC reference diagram")

## What is CIDR?

- **CIDR**  is Classless inter-domain routing. This will decide how many subnets you want to launch in a machine (VPC). Inside these subnets we can launch our machines. It contains the range of IPs i.e. IPv4 and IPv6.

###### IPv6 - 128 bits
###### IPv4 - 32 bits
`x.x.x.x/16 - x.x.x.x/28` (choose any value between this CIDR range)

Suppose,
`10.0.0.0/16 = 32-16=16 ==> 2^16= 65536` (65536 IP can be launched in 1 VPC of 16 CIDR value)

`10.0.0.0/24 = 32-24= 8 ==> 2^8= 256`
<br/>
`10.0.0.0/28= 32-28= 4 ==> 2^4= 16`

- A minimum 16 subnets and maximum 65536 subnets can be launched in 1 VPC.

- If your requirements is for more subnets then choose lower CIDR value and if requirement is less then choose higher CIDR value.

## Benefits of VPC
- Define custom networks.
- Assigns static private ipv4 addresses to the instances.
- Define network interfaces and attach one or more network interface to the instance. Define routing between different subnets.
- Define internet access for the subnets.
- Define your network security by allowing/denying the traffic.

<br/>

In this article, we discussed what VPC is and how does it work along with some of its benefits. In the next article, I will be discussing how to configure VPC in AWS and the steps to delete it once we are done tinkering with it. Stay tuned for the next article!


-------
<br/>


*Shreya Dhange is a Technical Training Developer at [Red Hat](https://www.redhat.com/en), who likes to explore and learn new technologies and share her knowledge by writing articles. She has completed her Masters in Computer Science and has gained award for her exemplary academic performance. She has been engaged in creating and delivering content in the cloud and linux space. She can be reached out [LinkedIn](https://www.linkedin.com/in/shreyadhange/) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=shreyadhange@gmail.com)*.


