What is System Design?
It is placement of different components and how they interact with each other.

- Learn how to design a Distributed System.
- Learn common algorithms, design patterns, tools that power distributed systems.

How to evaluate any System Design?
- Simplicity - Design should be understandable.
- Fidelity - Are all the requirements met by given design?
- Cost Effectiveness - Is the design affordable, feasible, implementation costs, any tooling required.

  Requirement - Create a Ecommerce Platform to sell T-Shirts
  Current Mode - Social Media or Offline
  New Requirement - Sell on Online Store as well

  Use Amazon?
  - Not able to customize look and feel of shop. Things are sold as products on Amazon.
  - No control over product recommendations.
 
  Use Shopify?
  - Gives resonable control
  - Own webpage
  - lot of integrations Shopify provides for payment providers, delivery providers.
 
  Issues with Shopify - 
- Issue with Delivery Tracking: Unable to track the ordered products. Expensive customer support. Need to check through Shopify Portal.
- Payment Gateway doesn't support international payments.

<b>Solution</b>

Create a Technical Wrapper over Shopify - Wrapper over existing solution, extracting functionality, more control, lesser bugs in new implementation.

Payment Page - Make a custom page to accept payments using payment gateway like PayPal, Stripe, Razorpay.

Order Tracking Page - Make a custom page to allow users to track their orders through order-id or tracking-id, users can view delivery status.


To support Payment Page we need to store information about success/failure of payemnts.

To support Order Tracking Page we need to know the current deluvery state.

This information is saved on the server, page with fetch data from server and display it to the user.


Pagement Page <----API----> Payment Server           

Order Tracking Page <----API----> Delivery Server


<b>API - Application Programming Interface</b>

An API for a server is a function, It takes some parameters as inputs and gives an output.

API can be written in any language of preference - Go, Java, Python etc.

Defines a contract betweeen Server and Application(Web Page or Mobile App) on how to send request and format of receiving response.

API Contract - Defines what kind of information needs to be send to the server to receive the response in desired format.


eg. Request for Payment Status
```
{
    "order_id": "ABC1234"
}
```

eg. Response for Payment Status
```
{
    "order_status": "success"
}
```

App -> sends request -> server running on some PORT receives request message -> serializes -> executes API function -> returns response.

