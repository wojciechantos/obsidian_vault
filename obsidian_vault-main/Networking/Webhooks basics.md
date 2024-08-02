
2024-07-29 | 08:08

##### Tags: [[Webhooks]] [[TAGS/Polling|Polling]]

---


> [!NOTE] What is a Webhook?
> A webhook is an HTTP-based callback function that allows lightweight, event-driven communication between 2 APIs. 
> 
> https://www.redhat.com/en/topics/automation/what-is-a-webhook


Webhooks are like notifications that allow to send messages between applications without need of short or long pooling. 

[[Networking/Polling]]

For example in the e-commerce app, when the user adds some products to the basket, proceeds to the payment and confirms the purchase. The client side (browser) sends the request to the payment service to process the payment. If for example the payment service is an external service by traditional way we would use short or long polling technique. 


> [!NOTE] Short Polling & Long Polling
> Short Polling term stands for the mechanism of a cyclical requesting a given service about the status of the operation.
> Long Polling is just the same as Short Polling 


When the operation is finished, the Webhook is triggered by the Stripe server to notify the client side about the payment operation status, so the client side can take the proper action and notify the user. 


