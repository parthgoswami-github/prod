# How AWS CloudFront works?


<br/>

In this article, we will see what AWS CloudFront is and in what scenario it is used. We will also take a look on some of its advantages and what edge locations are. 

<br/>

- Let’s consider an example where the user is searching for a website suppose www.primevideo.com and their request and response time should experience least latency.
- Now, if the amazon server is in the US and the user accessing prime video website is from California so they will experience less latency i.e 2 secs. This is due to less geographical distance between the system generating the request packet and server responding to the request
- Now if the user is from APAC (say India) and wants to access the same website, they are more likely to experience increased latency, assume 5 secs. 
- To solve this problem Amazon has introduced CloudFront service which works on the principal of CDN (Content Delivery Network).
- CloudFront leverages the edge locations nearest to your system generating the request packet, which helps in content delivery. 
- Basically it will cache your data and stores the data so that the other users, from the same geographical region as that of primary user, requesting for the same website will have less latency.
- It is cost effective and data sync is reliable.
- Edge location will fetch the data faster because it has high bandwidth.
Understand the difference that **Availability Zones [AZ]** are set of data centers that hosts servers, websites, applications, analytics, data processing etc, while **Edge Locations [EL]** are the data center that primarily are used to cache the data and provide a better user experience by reducing the latency. 

<br/>

![ ](/images/cloudfront/cloudfront.png " ")

<br/>

In simple terms, AWS CloudFront is a fast CDN service that securely delivers data with low latency and high speed transfer of data. You can create CloudFront in any specific region which helps keeping persistent connection with the origin.

## How Edge location works?

- As we discussed, edge locations are the data centers that host the web content. 
- Edge location will transfer less requested data to regional edge location.
- If regional edge location has has deleted it then edge location will request it from the origin.

As of writing this article, to deliver content to end users with lower latency, Amazon CloudFront uses a global network of 410+ Points of Presence (400+ Edge locations and 13 regional mid-tier caches) in 90+ cities across 47 countries.

## Advantages:

- Reduces the latency
- It is cost effective.
- Securely transfers data at fastest speed.
- High availability and scalability.
- Shows real time metrics and logging.

## How AWS leverage CloudFront for its own use? 
Transfer Acceleration takes advantage of the globally distributed edge locations in Amazon CloudFront. As the data arrives at an edge location, the data is routed to Amazon S3 over an optimized network path.


Stay tuned to learn more about its configuration in the next blog




-------
<br/>


*Shreya Dhange is a Technical Training Developer at [Red Hat](https://www.redhat.com/en), who likes to explore and learn new technologies and share her knowledge by writing articles. She has completed her Masters in Computer Science and has gained award for her exemplary academic performance. She has been engaged in creating and delivering content in the cloud and linux space. She can be reached out [LinkedIn](https://www.linkedin.com/in/shreyadhange/) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=shreyadhange@gmail.com)*.

<br/>

*[Parth Goswami](https://www.linkedin.com/in/parth-goswami/) is an opensource enthusiasts and likes to talk abot AWS and cloud computing.*

