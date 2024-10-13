# graphql-weather-service
A k8s microservice providing a GraphQL API proxy for the RESTful service at https://www.weather.gov/documentation/services-web-api

The purpose of this service is to create a GraphQL facade in front of the National Weather Service's RESTful API.
This will be designed as a Kubernetes microservice running under AWS EKS. 
Internally, this will be written in Java using Spring Framework.
Netflix DGS will be used to generate boilerplate Java code for query renderers from the GraphQL schema.
Redis will be used as needed to cache data extracted from the RESTful API, with a suitable TTL. 
Redis may also be used to implement resiliency features such as circuit breaking and rate limiting to guard against DDoS attacks.
