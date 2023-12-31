# React-Kube-e-commerce-app
A React e-commerce application with a microservices architecture, which contains two NodeJs APIs, a MongoDB database, a RabbitMQ messaging queue, and an integration with Twilio for SMS notifications. This was deployed via AWS EKS.

## _The purpose of this app is to explore Kubernetes deployments_

<img width="734" alt="Screenshot 2023-09-11 at 20 43 33" src="https://github.com/VladC24/React-Kube-e-commerce-app/assets/36422289/5b6363d3-4a18-4881-a187-b257d8df36ca">

### APIs:
- products-API
- notifications-API

### How it works:
- the _products-API_ communicates with the React client to send and pull all the products from the database.
- the _products-API_ then communicates with the _notifications-API_ via the messaging queue
- the _notifications-API_ sends via Twilio an SMS to the user (e.g. "Item has been delivered")


<img width="997" alt="Screenshot 2023-09-10 at 11 22 35" src="https://github.com/VladC24/React-Kube-e-commerce-app/assets/36422289/304807f2-2cac-400d-a897-54b82ff7b8b1">

### Kubernetes
- Created deployment files for each of the pods
- Created cluster ip services for each pod for connections - notifications-api does not have one as it only listens to the RabbitMQ messaging service.
- Added Twilio secrets in Kubernetes secrets
- Created RabbitMQ configmap
- Created the Nginx ingress
- Created persistent storage for mongodb
- Created EKS cluster with t2.medium nodes (EC2)
- Created the secrets for app use in the new EKS cluster
- Created AWS ingress

<img width="643" alt="Screenshot 2023-09-11 at 18 17 32" src="https://github.com/VladC24/React-Kube-e-commerce-app/assets/36422289/4153978f-ec2b-4c3d-a402-7fb9d5ec3271">

