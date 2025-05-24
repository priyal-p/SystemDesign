Whether to go for a Monolith or a Microservice Architecture?
<img width="1049" alt="Screenshot 2025-05-23 at 5 59 04 PM" src="https://github.com/user-attachments/assets/840a1667-9013-4789-9b99-a8bf1214d145" />

Monolith vs Microservices

Whether to choose Node.js or Python? Is Node.js slow?
For General operations - Node.js is 2-4 times slower than other optimized languages.
We would have to pay CSP more money for servers for more compute.
If resources with Node.js knowledge is cheaper and easier to train than that cost can be offset. It might be better for the business.

Focus on -
- Think about tradeoffs
- Talk with numbers
- Do a cost-benefit analysis with the founder or product manager.

---

Implementing a new feature
Capacity Estimation
1. Cost of implementing a new feature?
- Tech Cost:

  Time and cost spend on the team

- Frequency Cost:

  How many users will use the new feature
  10000 users visit site -> 10% try out the feature -> 1000 API calls to new service 
  Average monthly cost of running the service = cost of 1000 API calls * 30

2. Cost of storing the required data?

  Avg Data to be stored = 1000 API Calls * 1 MB (Avg file size) = 1 GB per day
  
  Avg total cost = 1 GB per day * S3's cost/file

---

Focus to -
1. Meet all requirements
 - simple
2. Optimizations

Capacity Estimation
- How much data we need to store?
- How much memory would be consumed?
- How much bandwidth is required?
- How many servers are required?

Public APIs for Developers to use the feature - 
People interact with the system through Public APIs
Complex API contract would make it difficult to understand the feature, prone to errors, lower adoption.

External visible code pieces - 
- API contracts
- Service Level Agreements (SLAs)
