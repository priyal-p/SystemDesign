What are Pages?

When users visit a website, they type the name of website and are redirected to the website's webpage, where they can perform certain actions like regsiter, login, create new account. These requests are handled by our server.

What is a webpage?
It is a static file which tells us how it is going to look like though HTML, CSS and how it is going to behave like through JS, or some way in which webpage can react to certain actions of a user.

A webpage is a file downloaded and displayed by the browser. The file is described using HTML, CSS and Javascript code.

This webpage can be stored in two places - 
1. CSP Servers - Serverless/Machine/Serverless Function
2. Content Delivery Network (CDN)

   Content Delivery Network
   -
   Servers are spread across the globe managed by Akamai, AWS Cloudfront, Cloudflare, so pages can be fetched very quicly as users can get the request handled through CDN located closer to their geographic regions.
   For regions with more users their can be more than one CDN to handle the higher number of requests. This is managed by content delivery network.
   Relatively cheaper to own solution of CDN as they have many clients so can offer services at relatively cheaper rates by amortizing costs.
   We get benefits of scale

   Static Pages are stored in these servers eg Images, files, videos etc are stored in CDN servers.

   Serverless
   -
   Implementing CDN like support can be difficult to setup, expensive, high operation costs, more testing efforts.

   Dynamic data is stored in databases and not on CDN Servers.

   Q. Why can we not store static as well as dynamic data on CDN servers?
   A. As CDNs are distributed across the globe (good for reducing latency) but this becomes a problem when we have to keep dynamic data consistent as reconcilation of changes in dynamic data may have some delay.
   Updates cause problem due to latecy as in a distributed environment passing data is difficult in real-time.
   Maintaining data consistency is highly difficult in CDNs

   Dynamic Data should be saved in servers acting as single source of truth and webpage should directly fetch the data from the server.

   Q. How fies are added to CDNs?
   A. We would need a file system that is consistently being read by the CDN and when it detects a new file added based on its id not matching any other existing file, it is added to all the CDN Servers.
   This file system can be on local machine or its better to have things in the cloud for higher reliability and relatively lower cost.
   Cloud storage can be through Amazon S3, it is a distrubuted file system. provides high durability, consistency, 
   Local storage can be through Hadoop file system.
   CEPH is also an open source file system - free and open-source software-defined storage platform that provides object storage, block storage, and file storage.

   For cloud based solution through AWS - Using Amazon Cloudfront with Amazon S3


   Domain Resolution
   www.cooltshirts.io -> ? Your Website

How does the internet works?
cooltshirts.io -> browser tries to resolve this address through Domain Name Server(DNS)


Device -> connected to Router(has IP address) -> Router has IP address of ISP -> Forwards users request to resolve domain "cooltshirts.io" to ISP -> ISP checks with DNS(It is a massive distributed network, has mapping of domain names with corresponding IP addresses)

DNS has mapping eg.
cooltshirts.io -> 192.1.1.5
facebook.com -> 192.4.6.3
.
.
.

Different domain name servers of different companies like GoDaddy, AWS Route53, interact with each other to resolve a domain name stored with them.

After domain name is resolved the user's browser gets the IP address of the website user is requesting. It is cached for future use. 

To load webpage of website on browser, now website requests its CDN(has some IP Address) to fetch webpage. CDNs can serve the request as they have this IP address.

Webpage is rendered on browser now.

Any user interaction on this webpage to perform certain operation like register, the request goes to server (Serverless etc)(has IP address cooltshirts.io server 192.1.2.3 in DNS), then response is received.

What database to use?
NoSQL or SQL

SQL is relatively mature, better for data analysis

   
   
