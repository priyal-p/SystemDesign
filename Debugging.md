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
