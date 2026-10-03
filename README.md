# Lab 2 - CST8915 Full-stack Cloud-native Development

**Name:** Angus MacGillivary  
**Course:** CST8915  
**Section:** 11 
**Lab:** Lab 2  
**Date:** October 3, 2026

## Service Codebases

[Product Service](https://github.com/macg0165/product-service)<br>
[Order Service](https://github.com/macg0165/order-service)<br>
[Store Front](https://github.com/macg0165/store-front)

## Video Demo

[Link](https://youtu.be/n9UoaTJPEII)

## Reflection Questions

**i. What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?**

Factors 3 and 4 both involve the loose coupling of connections between app services.  Factor 3 requires that no config be hardcoded in the app. Factor 4 requires that backing services be treated the same regardless of how they are hosted (locally or by a third party).  Factors 4 was achieved for the order service by replacing hardcoded URI connection string for RabbitMQ with a reference to an environment variable. Factor 3 was achieved for each service by replacing references to port numbers with references to environment variables.

**ii. Why is it important to use environment variables instead of hard-coding configurations in your application?**

Using environment variables instead of hard-coded config simplifies an app's lifecycle by seperating dev concerns of ops concerns.  This allows dev and ops teams to perform their function without having deep knowledge of the other end.  Additionally, separating config from VCS systems keeps to code history cleaner and easier to manage.

**iii. Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?**

Seperate repositories allows each microservice to be developed without needing to refer to other services.  This is valuable has organizations grow, and some services require more attention than others.  Teams for one microservice don't need access to the entire system to develop their section.  This also offers security benefits, as less inter-team access is needed.
