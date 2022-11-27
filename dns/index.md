# What is DNS?

## Domain Name System 

With over 8 billion cellphones worldwide (not including other devices), it is hard to correctly recall everyone's names and contact information. Because of this, the Domain Name System—or more precisely, the Phone Directory for IP Addresses—was introduced. However, due to the memory limitations of the human brain, we are unable to recall all of these billions of IP addresses. In order to make it easier to remember names, we began referring to these IP addresses by names, which are simply the website names that we type into the address bar of a browser. The task of determining which name is associated with which IP address is handled by DNS.

To put it simply, it maps the Name to the available IP addresses. Everyone who uses a digital device and the internet uses DNS, or domain name system, without knowing(not that they need to) how it enables them to find the exact content they are seeking online. Take  an example that you have no idea what a phone book is. How will you remember all of the contact details of everyone you meet and try to stay in touch with? This is essential if you want to be able to reach the specific person you want to. Indeed, you can't do it properly, which is how the idea of a phone directory emerged.

Similar to this, the digital gadgets we use every day, such as smartphones, routers, speakers, and other items that may connect to the internet, have their own naming conventions. These names are referred to as IP addresses.

![ ](/images/visiting_authors/gaurav_kale/dns/dns_2.png "")


Coming to the technical part of how it works and get us the IP address, where it gets the IP address from?
Let us first know the components and jargons that are involved in the above process.

## Components and jargons

#### DNS recursor 
The recursor might be likened to a librarian who is asked to search a library for a certain book. A server called the DNS recursor is made to take requests from client devices using software like web browsers. In most cases, the recursor is then in charge of sending further queries to respond to the client's DNS query.

#### The Root nameserver
 It is the first place where human readable host names are converted (resolved) into IP addresses. It can be compared to an index in a library that directs users to various book racks; often, it acts as a pointer to other, more precise locations.

#### The top-level domain server (TLD)
Can be compared to a particular shelf of books in a library. The final part of a hostname is hosted by this nameserver, which is the following stage in the process of locating an IP address (in the case of example.com, the TLD server is "com").

#### Authoritative nameserver
This last nameserver can be compared to a dictionary on a shelf of books, where a name's definition can be found. The final stop in the nameserver query is the authoritative nameserver. The IP address for the requested hostname will be returned to the DNS Recursor (the librarian) who initiated the initial request if the authoritative name server has access to the requested record.


## Step that make up a DNS lookup:
1. A user types "example.com" into their web browser, which sends the query out over the Internet and into a DNS recursive resolver.
2. A DNS root nameserver is then questioned by the resolver (.).
3. The Top Level Domain (TLD) DNS server address (such as.com or.net), which holds the data for its domains, is then returned to the resolver by the root server. Our request is directed at the.com TLD while looking for example.com.
4. After that, the resolver sends an inquiry to the.com TLD.
5. The TLD server then replies with example.com's nameserver's IP address.
6. The recursive resolver then queries the nameserver for the domain.
7. The nameserver then provides the resolver with the IP address for example.com.
8. After that, the DNS resolver replies to the web browser with the IP address of the domain that was originally requested.

And after this, the browser is able to get the data for the website and display it to the user.

## Types of Queries:
#### 1. Recursive query
In a recursive query, a DNS client expects a DNS server (usually a DNS recursive resolver) to respond with either the requested resource record or, in the event that the resolver is unable to locate it, an error message.                                                                                                                                                       
#### 2. Iterative query
  In this case, the DNS client will let the DNS server give the best response it is able to. A referral to a DNS server authoritative for a lower level of the domain namespace will be returned if the queried DNS server does not have a match for the query name. The recommendation address will then be contacted by the DNS client. Up the query chain, this process is repeated with other DNS servers until an error or timeout happens.

![ ](/images/visiting_authors/gaurav_kale/dns/dns_3.png "")

Hope this article was helpful. Happy learning :)

-------
<br/>


*Gaurav Kale can be reached out on [LinkedIn](https://www.linkedin.com/in/gaurav-kale-74629b199), [Twitter](https://twitter.com/kale_gauravv) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=kalegaurav111@gmail.com)*.

