Should we host code on Local Machine or Cloud Service Provider?
Both have Fidelity

Local Server
1. Less Reliable - Relatively not easy to replace when hardware crashes.
2. Difficult scenarios like power outage, not being able to remotely access computer leading to service issues.
3. Lower simplicity
4. High cost of implementation

CLoud Service Provider
1. More Reliable - Can spin up a new machine if one crashes.
2. Provide managed instances
3. Higher Simplicity as CSP manages our instance eg manage deployments, operating updates.
4. Low cost of implementation


Cloud Service Provider is better as compared to Local Server.

Two major approaches with Cloud Service Provider -
1. Serverless - Entire instance managed end to end by the CSP. Write the code and tell the CSP to run it on the server. We don't even care about compilation and deployment.
We are not aware of 
- the type of server, or
- the OS of server, or if 
- the server is currently running or not. 
we just know that when a request comes, it would be handled in a given time frame. CSP handles the execution of code by itself end to end.
Let's developers run the code without managing servers as the Cloud Service Provider handle everything. eg. Azure, AWS, GCP

2. Server - Hosting a server by ourseleves on the cloud, many things managed by CSP like OS installation, versioning, upgrades.But if server crashes we would have to turn it on through CSP GUI or command line interface. 
This requires users to manage their own servers for hosting applications and handling scaling.

   Server
   1. Lower ease of use (setup, scaling, maintainence)
   2. Higher efficiency, Relatively cheaper, Can handle more requests for same amount of money.
   3. Higher Responsiveness, We can reserve capacity and scale before any major event to be prepared for higher request load, reducing latency
  
   Serverless
   1. Higher ease of use
   2. Lower efficiency
   3. Lesser Responsiveness, CSP can take some time to scale up/down based on request load. This might cause some latency when the new instances are being spin up when request load is high.
  
      For smaller businesses Serverless might be suitable.
