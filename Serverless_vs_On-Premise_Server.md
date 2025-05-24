
Serverless vs On Premise Server
 With the number of users increasing cost hosting the app on CSP is increasing.

To reduce costs -
- Get credits from AWS - AWS Credits are promotional funds offered by Amazon Web Services (AWS) to help offset the cost of cloud services. They are available through various programs like AWS Activate and can be applied to eligible services, reducing the financial burden for startups, nonprofits, students, and others. 
- Run code more efficiently - caching data, reducing compute, I\O, memory. Reduce impact of serverless application
- Infrastructure -

Why Serverless is expensive?
Because it manages end to end services for us like hosting, deployments, fault tolerance etc.

Managing all this by ourselves would be costly and difficult.

- We can host servers on-premise - Host and manage our own servers. (Costlier and Difficult to manage)
- We can migrate to another CSP with better pricing.(Last option)
- We can reserve instances on CSP so that no one else would use these servers. This will make the billing on a yearly basis, usually discounted, reducing costs. These servers would also have Public APIs exposed, But we would have to manage these servers ourselves eg starting server, stopping server, upgrading code on server, deploying code on the server.

API - api.cooltshirts.io/purchase?id=23456&userId=1234 

Request to above API has to be routed to our server.

api.cooltshirts.io -> This helps in resolving the request to our server. Our purchased/reserved instance would have an IP Address(eg. 192.3.4.5). This IP Address is configured in AWS Route53 DNS provider. DNS has mapping of api.cooltshirts.io to 192.3.4.5

On receiving request, server calls purchase function, and passes the query parameters passed in the GET request ()GET request parameters are passed to the function in consideration). We can also send authentication parameters in the request as request headers.
Postman is a platform for developers to design, build, test and collaborate on APIs

How to setup the reserved server?
This setup can be done through GUI for any CSP eg. AWS, GCP, Azure.
We can also control the settings of these instances like size of instances eg. nano, small, medium, large, 2xlarge, 4xlarge

We can get a large instance and with to and fro monitoring the usage we can reduce the size based on compute utilization
In code repository we can set up events based on which the server would take latest pull of code and restart itself. After restarting the server, all in-memory data of server is deleted and we have an updated instance.

After some time, we observe server crashes, slow response time for users. Upon checking we identify that this is not a bug, but the memory/compute utilisation is very high.
We need more compute power, we go for larger instance to 2xlarge then after sometime upgrading to 4xlarge due to more compute requirement with growing user base.

With scaling up the server with more compute power we see that in non peak hours we are not utilising the compute power of the server fully but we are paying for a large server.

Problem if we just keep purcahsing larger instances - 
1. We are not able to reserve capacity efficiently.
2. No availability of auto-scaling leading to under utilization by reserving a large instance.
3. A single server instance is a single point of failure.
4. Using a fleet of smaller servers instead of one large server provides more computation power in the same amount of money.
   32 small computers -> Each giving 2 Virtual Machines -> 64 Virtual Machine
   1 4xlarge computer -> 32 Virtual Machine

   For parallelization a bunch of small computers is better than one large computer.
   Single large computer with multiple cores becomes impractical.

   Problems with multiple small servers -
   1. Redirecting of requests incase one of the instances crashes - If one of them crashes how would the requests directed to that server would be redirected.
   2. Judiciously utilizing all the resources available - sending equal amount of requests to all the servers so that wait time of requests is even, not overloading a particular instance, sharing load among servers.
      This can be handled through a Load Balancer.Load Balancer sends the request to the most optimal server. This can be through a random selection, or using Round Robin approach.

      For low latency, servers can be placed in regions where the number of requests is high, reducing the latency of requests for the users of those regions as the closest server can handle the request. But the central Load Balancer should be able to redirect the request to other servers even in another region if the server in the closest region has crashed.
   
<img width="908" alt="Screenshot 2025-05-24 at 9 32 28 PM" src="https://github.com/user-attachments/assets/3319514f-2eac-4ede-b97c-d8dede82f67a" />

<img width="873" alt="Screenshot 2025-05-24 at 9 35 17 PM" src="https://github.com/user-attachments/assets/e9e0fa49-1a63-41e2-85ce-5d3a2359e42a" />

<img width="646" alt="Screenshot 2025-05-24 at 9 37 41 PM" src="https://github.com/user-attachments/assets/a7fb4b87-ffa0-4250-8507-a9f424a729fc" />
