# Certified Calico Operator: Level1


In this article, I will share my experience in becoming a [Certified Calico Operator: Level 1](https://www.tigera.io/lp/calico-academy-completion/). Most of the information is available on the course portal and Calico’s webpages. I've made an effort to compile all the essential details about the course and exam in one location, and I hope it will be helpful to you.

<a href="/images/ccol1/kubecuddle.png" target="_blank"><img src="/images/ccol1/kubecuddle.png" width="300px" align="right" /></a>

## What is Project Calico? 

Project Calico is an open-source project with an active development and user community. Calico Open Source was born out of this project and has grown to be the most widely adopted solution for container networking and security, powering 2M+ nodes daily across 166 countries.

## What does the course cover?

This course will cover how Kubernetes networking works, how to configure and manage a Calico network, and how to secure your Kubernetes cluster.

- **Introduction to Kubernetes Networking**
- **Installing Calico**
- **Everything you need to know about Network Policy, including:**
	- Introduction to Network Policy
	- Best Practices for Network Policy
	- Managing Trust Across Teams
	- Network Policy for Hosts and NodePorts
- **Everything you need to know about network connectivity, including:**
	- Pod Connectivity Fundamentals
	- Calico’s Next Generation eBPF Dataplane
	- Encrypting Data in Transit
	- Fun with IP Address Management
	- Peering with BGP
- **Everything you need to know about Kubernetes Services, including:**
	- Introduction to Kubernetes Services
	- Understanding Kube-Proxy Service Handling
	- Understanding Calico Native Service Handling
	- Advertising Services

## Key highlights of the course: 

- Self Paced
- Lab-Based
- Free
- Certification after competition of course
- Deep dive to K8s Networking and Security policy
- Calico CNI
 

 
## Let’s breakdown the course content: 

The course is self paced and nominally structured into 4 weeks. Each week will take around 2-4 hours to complete depending on your level of experience. So you can work at a relaxed pace one or two evenings a week, and still complete the whole course in 4 weeks.  However, you are welcome to progress at whatever pace works best for you, including completing the whole course in a single day if you would like to.
 
Each week covers a different area of learning and consists of a combination of short video presentations and step-by-step guided hands-on labs. 
 
There’s a short quiz at the end of each week so you can test your knowledge as you progress through the course. These do not count towards your certification and are there solely to help you cement your learning. Finally there is a graded exam at the end of the course that you must pass to obtain your certification.
 
- **Week 1**
	- Kubernetes Networking Introduction
	- Lab Setup
	- Installing Calico
	- Installing the Sample Application
	- Managing Your Lab
	- Test Your Knowledge
- **Week 2**
	- Introduction to Network Policy
	- Why use Calico for Network Policy
	- Best Practices for Network Policy
	- Network Policy Fundamentals
	- Managing Trust Across Teams
	- Network Policy for Hosts and NodePorts
- **Week 3**
	- Introduction
	- Introduction to Pod Connectivity
	- Pod Connectivity Fundamentals
	- Encrypting Data in Transit
	- IP Pools and BGP Peering
	- Choosing the Best Networking Options
- **Week 4**
	- Introduction
	- Introduction to Kubernetes Services Networking
	- Understanding Kube-Proxy
	- Understanding Calico Native Service Handling
	- Advertising Services
	- Test Your Knowledge
 
## Are there any prerequisites? 

The course assumes you are already reasonably familiar with the basic Kubernetes concepts such as pods and namespaces, though you definitely don't have to be a Kubernetes expert.
In-depth networking knowledge is not required. If you know what an IP address is, what DNS is, and what a load balancer is, then you know more than enough already. 
 
## Why did I take this course? 

I come from the Networking background.  worked for Red Hat for about four years before moving on to Cloudera. During that time, I spent a significant amount of time on networking and began working with containers and kubernetes. I could therefore relate to Project calico's products and solutions because I was familiar with networking, cloud native, and containers. This made me want to explore Calico's cloud-native based open source solution on networking kubernetes.
 
## Taking the course: 

The course helped me revise some of the networking concepts such as kubernetes network policy, pod connectivity, Kubernetes DNS, outgoing NAT and some other key concepts such as IPv6 and dual stack, ingress and egress. Ofcourse, there are many more concepts throughout the course which explain in detail about Calico’s CNI, it’s working and advantages. 
 
## Taking the exam: 

The exam has four sections: Kubernetes Networking, Networking Policy, Pod Connectivity, and Kubernetes Services. It has about 70 questions. If you understand the fundamentals of Kubernetes networking and have done your homework by studying the course well, you should be able to pass the exam on your first try. There are a variety of question types, including true or false, multiple choice, and while some questions have multiple options with two or more than two correct answers. The exam tests your overall understanding about the concepts covered in the course content. You can check your score after submitting all of your responses, and if you passed, you can download the certificate.

![](/images/ccol1/ccol1.png " ")

<br/>

## My key takeaways from the course: 

- Calico supports both namespaced network policy, and a non-namespaced global network policy. 
- Unlike Kubernetes, where the action is implicit allow, Calico allows to explicitly specify allow or deny actions. 
- Calico can be installed as part of the hosted kubernetes platform on all major cloud providers such as EKS, AKS and GKE. 
- Calico can provide both overlay and non-overlay networking. 

I would like to strongly recommend the [Certified Calico Operator: Level 1](https://academy.tigera.io/course/certified-calico-operator-level-1/) course for everyone interested in Kubernetes networking.

## Explore other certifications from Project Calico: 

- [Certified Calico Operator: eBPF](https://academy.tigera.io/course/certified-calico-operator-ebpf/)
- [Certified Calico Operator: AWS Expert](https://academy.tigera.io/course/certified-calico-operator-aws-expert/)
- [Certified Calico Operator: Azure Expert](https://academy.tigera.io/course/certified-calico-operator-azure-expert/)

Next up, I will be studying the **Certified Calico Operator: AWS Expert** course and taking the exam.

![](/images/ccol1/bigcat.png)

Hope this article was helpful. Stay tuned for the next blog and happy learning!!👋🏻

