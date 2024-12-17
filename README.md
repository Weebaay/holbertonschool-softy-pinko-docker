### Project Badge: Docker  
**Difficulty Level**: Novice  
**Weight**: 1  
**Manual QA review** must be done (request it when you are done with the project).

---

## Project Overview

Docker is a platform that enables you to containerize applications, creating portable, self-contained environments that can run anywhere. This project leverages Docker to set up an infrastructure for an application with multiple servers, utilizing reverse proxy, load balancing, and application servers. You will configure Docker containers to run a reverse proxy, a load balancer, two application servers, and one front-end static-content server.

---

## Context

With Docker, you can encapsulate your applications into containers, which include everything needed to run the application—such as libraries, dependencies, and configuration files—inside an isolated environment. This allows seamless movement of applications across different environments, such as local machines or servers, without the need to worry about dependencies or configurations.

In this project, you will be working with Docker to:

- Set up a reverse proxy server to route traffic.
- Implement a load balancer for API servers using the Round Robin algorithm.
- Set up front-end static-content server.

This project involves the creation of a multi-server architecture within Docker.

---

## High-Level Design

The architecture consists of a single server acting as the entry point for the application. The server performs two functions:

1. **Reverse Proxy**: It routes incoming traffic either to the API servers or the front-end static-content server.
2. **Load Balancer**: It balances traffic between two API servers using the Round Robin load balancing algorithm.

### Flow Overview

1. **Front-End Static-Content Requests**:
   - Requests directed to the front-end server will be routed through the reverse proxy, which fetches static content and sends it back to the client.
   - The client does not communicate directly with the front-end server.

2. **API Requests**:
   - Requests to the API servers are routed by the reverse proxy.
   - The proxy load-balances the requests between two API servers using Round Robin. This ensures equal distribution of traffic to prevent server overloads.
   - The client interacts with the proxy, not directly with the API servers.

### Round Robin Load Balancing

Round Robin is a method of load balancing where requests are distributed evenly across servers. For example, if there are three servers (A, B, and C), the requests are routed in a rotating manner:
- The first request goes to server A, the second to server B, the third to server C, and so on.
- This cycle repeats as the load balancer continues to distribute traffic evenly.

Round Robin load balancing is a simple yet effective strategy for distributing traffic in situations with relatively equal workload distribution.

---

## Prerequisites

Before starting this project, ensure you have the following:

- **Docker Desktop** installed on your local machine.
  - [Docker Desktop Download](https://www.docker.com/)
  - Detailed installation instructions:
    - [Windows](https://docs.docker.com/desktop/install/windows-install/)
    - [Mac](https://docs.docker.com/desktop/install/mac-install/)
    - [Linux](https://docs.docker.com/desktop/install/linux-install/)
    - Chromebook: Note that Docker Engine is available for Linux, but Docker Desktop may not be fully supported.
- Basic familiarity with Docker.
  - Recommended Docker Tutorial: [Docker Tutorial](https://www.docker.com/resources/what-container/)
  
### Useful Resources
- [Docker Cheatsheet](https://dockerlabs.collabnix.com/docker/cheat-sheet/)
- [Proxy vs Reverse Proxy - Real World Examples](https://www.cloudflare.com/learning/cdn/glossary/reverse-proxy/)
- [What is a Reverse Proxy?](https://www.youtube.com/watch?v=ApU3QfdYXmI) (Stop at 06:25)

---

## Project Structure

This project will include the following components:

- **Reverse Proxy Server**: Handles incoming requests and routes them to the appropriate service (API or Front-End server).
- **Load Balancer**: Implements the Round Robin algorithm to distribute requests evenly across two API servers.
- **Two API Servers**: Handle application logic and serve API responses.
- **Front-End Server**: Serves static content such as HTML, CSS, and JavaScript files.

You will configure each of these components in Docker containers to work together as an integrated system.

---

## How to Run the Project

### Step 1: Clone the Repository

Clone the project repository to your local machine:
```bash
git clone hhttps://github.com/Weebaay/holbertonschool-softy-pinko-docker.git
cd task0 / task1 / task2 / task3 / task4 / task5 / task6
```

Step 2: Build and Run with Docker Compose

Run the application using Docker Compose. This will spin up all the necessary services.

docker-compose up --build

This will start the following services:

    Reverse Proxy Server
    Load Balancer
    API Servers (2 instances)
    Front-End Static Content Server

Step 3: Access the Application

Once the services are up and running, you can access the application by navigating to http://localhost in your web browser.

    Front-End: Static content will be available on the main page.
    API: API requests will be routed to the API servers via load balancing.

## Author

Created by: **Jean Paul Dijeont**
## License

This project is licensed under the MIT License - see the LICENSE file for details.

