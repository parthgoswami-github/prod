# Amazon EKS: A managed Kubernetes service by AWS




Kubernetes won the race to become the de-facto container orchestration engine. Ever since, a lot of companies are coming up with their own version of container orchestration based on top of Kubernetes, while, some other companies are developing tools and products to complete the Kubernetes in the orchestration space. 

Having said that, the top three cloud provides, have come up with their own version of managed Kubernetes offerings: 
- Microsoft Azure offers the **Azure Kubernetes Service (AKS)**
- AWS offers the **Amazon Elastic Kubernetes Service (EKS)**
- Google Cloud offers the **Google Kubernetes Engine (GKE)**

## What is Amazon EKS? 

Amazon Elastic Kubernetes Service (Amazon EKS) is a managed service that you can use to run Kubernetes on AWS without needing to install, operate, and maintain your own Kubernetes control plane or nodes. **Kubernetes** is an open-source system for automating the deployment, scaling, and management of containerized applications.

In June 2018, AWS made EKS generally available for all. EKS is similar to AKS and GKE as it supports swift development and deployment of applications based on Kubernetes.

Let's take a look at some of the critical areas to understand how EKS behaves as a managed Kubernetes service. 

## Updates

Updating EKS requires multiple steps to be implemented. The users of EKS need to run instructions via command-line, which initiates the update. These steps are required to manage the updates for nodes. 

## Resource monitoring

AWS offers lightweight monitoring for the control plane directly in Cloudwatch. To monitor the workers, you can use Kubernetes Container Insights Metrics provided via a specific CloudWatch agent you can install in the cluster.


## Availability

AWS  has 66 availability zones. And the footprint will increase as Amazon plans to add 12 more zones to its total tally of AZs. 

## CLI Support

The official user guide also uses the following command line tools: <br/>

`kubectl` – A command line tool for working with Kubernetes clusters.<br/>
`eksctl` – A command line tool for working with EKS clusters that automates many individual tasks.<br/>
**AWS CLI** – A command line tool for working with AWS services, including Amazon EKS.

Creating a cluster via `eksctl` is as easy as `eksctl create cluster`, no other parameters required.


## Node Pools
In a cluster of K8s, a group of nodes that share the same configuration are referred to as a node pool. Node pools are vital as they allow the cluster to function with different machines for various workloads. The users can designate the node pools with the service they want to deploy them with.

EKS allows its users to run 100 nodes per node pool. 


## Auto-Scaling

One of the standout features of Kubernetes is its seamless ability to scale the nodes. This enables the cluster to trim down on resources usage. This not only saves time but is also cost-effective as both heavy and lean demands are met with the right amount of resources. Additionally, Auto-scaling can be utilized to tweak the resource utilization plans for the present and future.

EKS autoscaling is relatively easy as it only takes a few manual steps. Also, it is the only one to allow bare-metal nodes to run your Kubernetes cluster.


## Pricing

EKS bills 10 cents/hour/control plane. Additionally, USD 0.20 per hour is billed for every deployed cluster. AWS doesn’t allow the use of their free tier to test an EKS cluster is that EKS requires bigger machines than the tX.micro tier, and EKS hourly pricing is not in the free tier.



Hope the article was useful, thanks for reading! 

