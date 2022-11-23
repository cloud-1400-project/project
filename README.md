# Cloud Computing Project
---
## Table of Content
1. [Overview](#o)
2. [Project Overview](#po)
3. [Micro-services](#ms)
4. [Phase 1](#p1)
5. [Phase 2](#p2)
---
<a id="o"></a>
## Overview
---
In the course of this project, you will be familiarized with the Go programming language, REST API development, micro-service architecture, GRPC, containerization using Docker, development-level deployment using docker-compose, and Kubernetes. Here are a few useful links to these technologies, and concepts:
1. [Go](https://go.dev/)
2. [REST](https://restfulapi.net/)
3. [micro-service arch](https://microservices.io/)
4. [Docker](https://www.docker.com/)
5. [docker-compose](https://docs.docker.com/compose/)
6. [Kubernetes](https://kubernetes.io/)
---
<a id="po"></a>
## Project Overview
---
First of all, you will be introduced to the fundamentals of the Go programming language, so that you possess the necessary skills for developing a simple micro-service. Then, you'll be given access to two fully implemented micro-services, which you'll add a third to, and their documentations. After you've familiarized yourselves with these micro-services, you'll develop a third that will complete their function. Finally, by utilizing docker-compose, you'll bring up the whole system, comprising databases, the two given micro-services, and your own service.

---
<a id="ms"></a>
## Micro-services
---
![o](https://user-images.githubusercontent.com/64916254/203114001-4062b7f9-4b85-45ce-83f1-073a9f72fb99.png)

Here in this diagram you can see what purpose each part serves. The authentication service, and the product service, are fully developed, containerized, and accompanied by the necessary yaml configuration for the docker-compose. Before moving on to the development phase, you need to read their documentations, and plan for the next phases. Here are the links to each service, and a master repository (some will be added soon):
1. [AUTH](https://github.com/cloud-1401-project/auth-service)
2. [PRODUCT]() --TO BE ADDED--
3. [Master Repo]() --TO BE ADDED--

### Notes
It is necessary that you read all the documentation of these services thoroughly, and carefully. The authentication service utilizes an access/refresh token pattern for authentication, and you can find a sample python script calling it's APIs in this [file](https://github.com/cloud-1401-project/auth-service/blob/master/python_helpers/helper.py). You can access it's documentation by either bringing up the service, and accessing localhost:port/api/docs, or by simply opening this [file](https://github.com/cloud-1401-project/auth-service/blob/master/docs/documentation.html) in a browser. It is highly recommended that you go with the former, as you have to take this step prior to development anyway.

---
<a id="p1"></a>
## Phase 1
---
The authentication micro-service handles all the necessary actions for managing user; including but not limited to:
1. Creating an account
2. Logging in
3. Handling authentication internal calls (GRPC)

The product micro-service works in a simple way:
1. It returns the list of the products to the an authenticated user through an API call.
2. It lets the order micro-service know whether a product is available -or even is valid-. (GRPC)

The order micro-service, which you'll implement, serves a simple purpose; it manages a cart. It's noteworthy that finalizing the transaction will be left unimplemented as it is beyond the course, and purpose of this project. Here is what this micro-service should do:
1. Let the user add an item to their cart, accounting for the availability of that item by checking with the product micro-service.
2. let the user modify their cart. (increasing/decreasing the quantity of an item or deleting them all together)

It's worth mentioning that you can just keep everything in the memory; you aren't required to use a database, but it might be considered a bonus point.

### Notes
You need to fork the [Master Repo]() and apply necessary changes to it, in addition to adding your order-service repository as a submodule. This forked master repository should contain all the necessary files, and configurations for bringing up all the components of the system.

---
<a id="p2"></a>
## Phase 2
---
Now that everything is implemented, all you have to do is to containerize your service by writing a Dockerfile, and then complete the given yaml configuration -the one in your forked master repository- to fully bring up the system. Just as it is with the rest of the components of this system, you need to apply memory usage, and cpu usage limits to your service. You can find the base Go image [here](https://hub.docker.com/_/golang/).

--- 

