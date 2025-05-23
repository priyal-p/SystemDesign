How to debug production issues?
1. Logging and Monitoring eg. AWS CloudWatch - All requests are logged, important operations eg database entry, communication to another system, logging response with response-id. Allows to trace a request from start to finish. GCP, Azure also have similar solutions. These logs are stored in a distributed store and can be queried through regex expressions.
2. Observabilty and Anomaly Detection

   eg Payment Gateway failures - Payment Gateway may have an agreement that only 98% of the payments would pass and 2% may fail.
   Average payment failure rate is 2%

   To resolve difficult and slow debugging of issues

    <img width="803" alt="Screenshot 2025-05-23 at 3 58 15 PM" src="https://github.com/user-attachments/assets/01db5d5d-b1e4-460e-a891-0221f698e9b1" />

    Logging Service and Log DB provided by AWS CLoudWatch
   
    <img width="703" alt="Screenshot 2025-05-23 at 4 00 23 PM" src="https://github.com/user-attachments/assets/51370db4-f321-43c6-8f0b-81bb0de727a0" />
    
   To identify sudden drop in sales, to identify the issue for such cases, we can build a dashboard which shows them the number of sales, number of visits, number of registrations per day. Looking at these visually may help the data analytics team to identify the issue and anomalies manually.
   Google Analytics(Free), Microsoft PowerBI(Paid), Salesforce Tableau(Paid)

   CSP allows integration with these analytics providers allowing us to emit events to Database, on top of which these Analytics dashboards can be built.

    <img width="926" alt="Screenshot 2025-05-23 at 4 04 24 PM" src="https://github.com/user-attachments/assets/7469c48f-b055-44da-9e66-b4cf9e2f9a46" />

Preventing Issues - 
Having backup payment gateway eg. PayPal, Stripe, Razorpay
<img width="917" alt="Screenshot 2025-05-23 at 4 16 39 PM" src="https://github.com/user-attachments/assets/259c97e3-8ebf-412b-8475-86e5a781f4b4" />

How reliable is the system?
- Identify points of failure, which on failing will lead to entire system collapsing?
  If CDN fails, webpages won't load, can't take orders.
  If Server fails, cannot fetch dynamic data, with serverless it is very less likely but if AWS has a problem then we will have a problem.
  If it is an external integration then we have an external dependency, and if it is in a critical path then we have a critical external dependency. Any external dependency is prone to failure.

  To ensure things continue working despite failures, How to avoid failures?
  1. Redundancy (Having multiple vendors and providers)
     1.1. Sereverless Server crashes, CSP will restart the server. CSPs are known for their reliability.
     1.2. Cloudfront or CDN very less likely to go down. Moving all services under one cloud like AWS, GCP, Azure as they are reliable.

     Backup DB
 <img width="993" alt="Screenshot 2025-05-23 at 4 32 43 PM" src="https://github.com/user-attachments/assets/9810c535-13eb-466e-adcf-520569d4c0fd" />

      Backup Payment Service provider
<img width="1002" alt="Screenshot 2025-05-23 at 4 37 57 PM" src="https://github.com/user-attachments/assets/84c44bcc-9f24-4bbd-8077-47d91619c0b1" />

 2. Graceful degradation
    If Shopify fails (Single Point of Failure), then we can show a messge to users that the site is down and will be back again, and log error in Logging, Analytics team to be able to check and identify issue.
Tell the customers that you are facing issues and inform them when you will be back, useful error messages help.
