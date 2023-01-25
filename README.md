# event-driven
In a money transfer, there are systems that check whether there is a fraud before the transfer. According to the monolotic system, the flow is as follows:

![image](https://user-images.githubusercontent.com/22428221/214672068-801009ed-4173-4c76-aed4-591199aed590.png)


The problem here is that when there is a problem in the call phase between services, it blocks one another.

According to the EDA structure, a transaction is sent to the topic on kafka before a payment is made and the fraud service listening to this topic performs the necessary business rules. The result is sent to the relevant topic in a validated way and the payment service that consumes it performs the transaction.

![image](https://user-images.githubusercontent.com/22428221/214672158-8a198fbd-77ac-4662-88a8-3905b86c28db.png)
