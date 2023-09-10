# React-Kube-e-commerce-app
A React e-commerce application with a microservices architecture, which contains two NodeJs APIs, a MongoDB database, a RabbitMQ messaging queue and an integration with Twilio for SMS notifications. 

## _The purpose of this app is to explore Kubernetes deployments_

### APIs:
- products-API
- notifications-API

### How it works:
- the _products-API_ communicates with the React client to send and pull all the products from the database.
- the _products-API_ then communicates with the _notifications-API_ via the messaging queue
- the _notifications-API_ sends an SMS to the user (e.g. "Item has been delivered")


<img width="997" alt="Screenshot 2023-09-10 at 11 22 35" src="https://github.com/VladC24/React-Kube-e-commerce-app/assets/36422289/304807f2-2cac-400d-a897-54b82ff7b8b1">

### Kubernetes
- Created deployment files for each of the pods
- Created cluster ip services for each pod for connections - notifications-api does not one as it only listens to the RabbitMQ messaging service.
- Added Twilio secrets in Kubernetes secrets
- Created RabbitMQ configmap


<img width="777" alt="Screenshot 2023-09-10 at 18 08 32" src="https://github.com/VladC24/React-Kube-e-commerce-app/assets/36422289/d4ea7221-1a53-4547-8a0e-3daee548afd1">
