# Cloud Computing Project
---
## Table of Content
1. [Sample Topic 1]()
2. [Sample Topic 2]()
---
## Overview
---
In the course of this project, you will be familiarized with the Go programming language, REST API development, micro-service architecture, GRPC, containerization using Docker, development-level deployment using docker-compose, and Kubernetes. Here are a few links to these technologies:
1. [Go](https://go.dev/)
2. [REST](https://restfulapi.net/)
3. [micro-service arch](https://microservices.io/)
4. [Docker](https://www.docker.com/)
5. [docker-compose](https://docs.docker.com/compose/)
6. [Kubernetes](https://kubernetes.io/)
---
## Project Overview
---
First of all, you will be introduced to the fundamentals of the Go programming language, so that you have the necessary skills for developing a simple micro-service. Then, you'll be given access to two fully implemented micro-services, which you'll add a third to, and their documentations. After you've familiarized yourselves with these micro-services, you'll develop a third micro-service that will complete their function. Finally, by utilizing docker-compose, you'll bring up the whole system, comprising databases, the two given micro-services, and your own service.
---
## Micro-services
---
Here in this diagram you can see what purpose each part serves. The authentication service, and the product service, are fully developed, containerized, and accompanied by the necessary yaml configuration for the docker-compose. Before moving on to the development phase, you need to read their documentations, and plan for the next phases. Here is the link to each service, and a master repository:
1. [AUTH]()
2. [PRODUCT]()
3. [Master Repo]()
---
## Phase 1
---
The authentication micro-service handles all the necessary actions for managing user; including but not limited to:
1. Creating an account
2. Logging in
3. Handling authentication internal calls (GRPC)

The product micro-service works in a simple way:
1. It returns the list of products to the end user through an API call.
2. It lets the order micro-service know whether a product is available -or even is valid-. (GRPC)

The order micro-service, which you'll implement, serves a simple purpose; it manages a cart. It's noteworthy that finalizing the transaction will be left unimplemented as it is beyond the course, and purpose of this project. Here is what this micro-service should do:
1. Let the user add an item to their cart, accounting for the availability of that item by checking with the product micro-service.
2. let the user modify their cart. (increasing/decreasing the quantity of an item or deleting them all together)

It's worth mentioning that you can just keep everything in the memory; you don't need to use a database, but it might be considered a bonus point.
---
## Phase 2
---
Now that everything is implemented, all you have to is to containerize your service by writing a Dockerfile, and then complete the given yaml configuration to fully bring up the system. Just as it is with the rest of components of this system, you need to apply memory usage, and cpu usage limits to your service. You can find the base Go image [here](https://hub.docker.com/_/golang/).
--- 

