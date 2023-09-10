# React-Kube-e-commerce-app
A React e-commerce application with a microservices architecture, which contains two Node APIs, a MongoDB database, a RabbitMQ messaging queue and an integration with Twilio for SMS notifications. This is deployed via Kubernetes.

### APIs:
- products-API
- notifications-API

### How it works:
- the _products-API_ communicates with the React client to send and pull all the products from the database.
- the _products-API_ then communicates with the _notifications-API_ via the messaging queue
- the _notifications-API_ sends an SMS to the user (e.g. "Item has been delivered")

  ![e-comm drawio](https://github.com/VladC24/React-Kube-e-commerce-app/assets/36422289/10a15cd7-f61c-4e72-843d-d5c0a4247a73)
