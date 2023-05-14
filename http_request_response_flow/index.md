# HTTP Request Response Flow


In the image below, we can see the names of every part in an URL.

![ ](/images/visiting_authors/gaurav_kale/http_request_response_flow/parts_of_url.png " ")

Previously we have discussed about what DNS is and how it works. In the HTTP(Hypertext Transfer Protocol) RR Flow, we will only be using the term on high level.

![ ](/images/visiting_authors/gaurav_kale/http_request_response_flow/rr.png " ")

Refer to the above diagram for a better understanding. When a end user hits a url, a TCP connection is first established with the server that is going to server the content. What is TCP connection!? TCP stand for Transfer control protocol and is basically a tunnel that is established between a client(end user) and the server.  Any request will flow or any communication will only take place within them only and only when there is a way or a tunnel through which they can send and receive requests, which is done by TCP Connection.

Let's learn more about TCP in another article.

After the connection is established, an HTTP request is sent to the server and that will contain a set of things.
The HTTP protocol is used to retrieve resources like HTML documents. It is the basis for all data interchange on the Web and operates on a client-server model, so requests must be made by the recipient, which is often a web browser.
After the request is sent to the server, it will respond with the content that is asked and it will serve. After the content is served, if there is a need to reuse the connection then we can otherwise the connection can be closed.

## Here is an example of HTTP request:

![ ](/images/visiting_authors/gaurav_kale/http_request_response_flow/http_request.png " ")

- An HTTP method, usually a verb like GET, POST, or a noun like OPTIONS or HEAD that defines the operation the client wants to perform. Typically, a client wants to fetch a resource (using GET) or post the value of an HTML form (using POST), though more operations may be needed in other cases.
- The path of the resource to fetch; the URL of the resource stripped from elements that are obvious from the context, for example without the protocol (http://), the domain (here, developer.mozilla.org), or the TCP port (here, 80).
- The version of the HTTP protocol.
- Optional headers that convey additional information for the servers.
- A body, for some methods like POST, similar to those in responses, which contain the resource sent.

## Example of HTTP response:

![ ](/images/visiting_authors/gaurav_kale/http_request_response_flow/http_response.png " ")

- The version of the HTTP protocol they follow.
- A status code, indicating if the request was successful or not, and why.
- A status message, a non-authoritative short description of the status code.
- HTTP headers, like those for requests.
- Optionally, a body containing the fetched resource.

That is an high level overview of how the request response flow happens for an HTTP request.

Now, the catch here is that all this flow is not very secure. Which is why we have **HTTPS**.

HTTP but secure is HTTPS. It may be just another word added to HTTP but it brings a lot of additional processes with it.

Let's first see what all these technical terms mean and then get the process sorted.

- **TCP Connection** : Transmission Control Protocol (TCP) is a standard that defines how to establish and maintain a network conversation by which applications can exchange data. TCP works with the Internet Protocol (IP), which defines how computers send packets of data to each other.

- **Client Hello** : The client initiates the handshake by sending a "hello" message to the server. The message will include which TLS version the client supports, the cipher suites supported, and a string of random bytes known as the "client random."

- **TLS** : It is a widely adopted security protocol designed to facilitate privacy and data security for communications over the Internet

- **Server Hello** : The server hello includes the server's certificate, digital signature, server random, and chosen cipher suite. Because it already has the master secret, it also sends a "Finished" message.
We will discuss other terms like CA(Certificate Authority), Certificates, master key in a separate session. (Let's Go with the basic meaning for now)

![ ](/images/visiting_authors/gaurav_kale/http_request_response_flow/flow.png " ")

## The process will be as follows:

Resuming from TCP connection, now there will be another process added and that will be the Client Hello. It will basically send a request to the server asking for its authentication and if it really is the server that is supposed to serve the content.

Then the server will send it's certificates to the client so that client can validate the authenticity of the server. This process is called Server hello. Also, there are ciphers involved which the client and server will decide to communicate in. After this process is done then all the communication will be done using the cipher and will totally be encrypted. 

This makes the requests and responses going to and fro very secure as compared to the HTTP. Hence HTTPS provides more security. This is called to be the SSL(Secure Socket Layer) connection.

Hope this article was helpful. Happy learning :)

-------
<br/>


*Gaurav Kale a tech enthusiast and a learner. He mostly deals with security and internet technologies and takes part in activities that can aid in promoting a better understanding of technology. In his free time, he enjoys reading books and watching movies. He can be reached out on [LinkedIn](https://www.linkedin.com/in/gaurav-kale-74629b199), [Twitter](https://twitter.com/kale_gauravv) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=kalegaurav111@gmail.com)*.

