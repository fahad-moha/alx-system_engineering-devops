# Application Server vs. Web Server - Readme

## Introduction
This document provides an overview of the infrastructure design that includes an application server and a web server. It explains the purpose of each component and discusses the reasons behind the addition of specific elements to the infrastructure. Additionally, it outlines the requirements for the infrastructure and the steps taken to meet those requirements.

## Infrastructure Overview
The infrastructure consists of the following components:

1. **Server**: This component represents a physical or virtual machine that hosts the application server, web server, and database server. It provides the necessary computing resources to run these components.

2. **Application Server**: The application server is responsible for executing server-side code and processing dynamic requests. It interacts with the database server, performs business logic, and generates dynamic content based on user requests. Separating the application server from the web server allows for better scalability, maintainability, and separation of concerns.

3. **Web Server**: The web server is responsible for handling HTTP requests from clients (browsers) and serving static content such as HTML, CSS, JavaScript, and media files. It responds to client requests by sending the appropriate files. Separating the web server from the application server allows for efficient serving of static content, reduces the load on the application server, and improves performance.

4. **Load Balancer**: The load balancer acts as an intermediary between clients (browsers) and the web server cluster. It distributes incoming client requests across multiple web servers to ensure optimal resource utilization, scalability, and high availability. By configuring the load balancer as a cluster, it enhances fault tolerance and reliability.

## Requirements and Rationale

The following requirements were considered in designing the infrastructure:

1. **Scalability**: The infrastructure should be scalable to handle increasing traffic and user demands. By separating the application server, web server, and database server onto their own dedicated servers, it becomes easier to scale individual components independently based on their specific requirements. This allows for efficient allocation of resources and ensures optimal performance.

2. **High Availability**: The infrastructure should be highly available to minimize downtime and ensure uninterrupted service. By configuring the load balancer as a cluster, it introduces redundancy and fault tolerance. If one load balancer becomes unavailable, the remaining load balancer(s) can continue to distribute traffic to the available web servers, preventing service disruption.

3. **Improved Performance**: Separating the web server from the application server allows for better performance by offloading the serving of static content to dedicated web servers. This minimizes the load on the application server, enabling it to focus on processing dynamic requests and improving response times.

4. **Maintainability**: Separating components onto their own servers enhances maintainability. Each component can be updated, patched, or restarted independently without affecting other components. It simplifies troubleshooting, debugging, and performance tuning.

5. **Load Distribution**: The load balancer is added to distribute incoming client requests across multiple web servers. This ensures that the workload is evenly distributed, prevents any single server from becoming overwhelmed, and enables horizontal scalability.

6. **Fault Tolerance**: By configuring the load balancer as a cluster, it introduces fault tolerance. If one load balancer or web server becomes unavailable, the remaining components can continue to serve traffic, minimizing the impact of failures.

7. **Redundancy**: Separating the components onto their own servers introduces redundancy. If one server fails, the remaining servers can continue to handle requests, ensuring service availability. This redundancy improves overall system reliability.

## Conclusion
The infrastructure design includes an application server, web server, and load balancer to meet the requirements of scalability, high availability, performance, and maintainability. By separating components onto their own servers and configuring the load balancer as a cluster, the infrastructure achieves fault tolerance, redundancy, and efficient load distribution. These design choices enable the infrastructure to scale, handle increasing traffic, and provide a reliable and efficient user experience.
