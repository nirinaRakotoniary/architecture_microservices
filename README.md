This repository implements microservices architecture with 4 main microservices : 
1 - product-service is the business layer of the project. We will run in inn three different port (e.g: 8080, 8081, 8082)
2 - config-service is the central configuration of all microservices and each microservice consult this one to get its configuration
3 - discovery service make each microservice visible for each other
4 - proxy-service is the proxy that handle the client's request and transfer it to one of the product-services running equitably

For testing, we need to run firstly the config-service, then the discovery-service, the proxy-service and lastly the product-service in more than one port.
In our case, we just need to launch request http://localhost:9999/product-service/messages in our navigator,the proxy will handle it and transfer to one product-service, then we can find message "c'est moi qui ai répondu!" logged in the service that handled the request.

When we launch more request, we can notice that it's distributed equitably for each product-service.
