# Three-Server Web Infrastructure with Load Balancer and Database Cluster

## Description
In this scenario, we will design a three-server web infrastructure to host the website www.foobar.com. The infrastructure will consist of two servers, a load balancer, a web server (Nginx), an application server, a MySQL database, and a set of application files. This design aims to improve the availability, scalability, and performance of the website compared to the previous one-server infrastructure.

## Infrastructure
The infrastructure includes the following components:

1. **Server 1**: This server hosts the web server (Nginx), which is responsible for handling HTTP requests and serving static content such as HTML, CSS, and JavaScript files. It receives requests for www.foobar.com and responds by sending the appropriate files to the user's browser.

2. **Server 2**: This server acts as the application server, running the server-side code of the website. It processes dynamic requests, interacts with the database, and generates HTML content to be served by the web server.

3. **Load Balancer**: The load balancer (HAproxy) distributes incoming requests across multiple servers to ensure efficient resource utilization and high availability. It uses a distribution algorithm (e.g., round-robin, least connections) to determine which server should handle each request. The specific algorithm chosen should be based on the specific needs of the application.

4. **Application Files**: This set of files contains the code base of the website's application. It includes server-side scripts, application logic, and any other necessary files to run the website's functionality.

5. **Database**: The MySQL database stores and manages the website's data. In this infrastructure, we will set up a Primary-Replica (Master-Slave) cluster for database replication. The Primary node serves as the active database, handling both read and write operations. The Replica node(s) replicate data from the Primary node and can be used for read operations to offload the Primary node and improve performance.

## Specifics of the Infrastructure

- The addition of the second server enables separation of concerns, with Server 1 dedicated to serving static files and Server 2 handling dynamic application logic.

- The load balancer is added to distribute incoming requests across both servers. It ensures that the workload is evenly distributed and helps prevent any single server from becoming overloaded.

- The load balancer is configured with a distribution algorithm (e.g., round-robin) that determines how requests are allocated to each server. The algorithm can be customized based on factors like server capacity, response time, or user session persistence.

- The load balancer enables an Active-Passive setup. In this setup, one server (e.g., Server 1) is actively serving requests while the other server (e.g., Server 2) remains passive and ready to take over in case the active server fails. The passive server continuously synchronizes data with the active server to ensure data consistency.

- The database is set up as a Primary-Replica (Master-Slave) cluster. The Primary node handles both read and write operations, while the Replica node(s) replicate data from the Primary node and can be used for read operations. This setup improves performance by offloading read operations from the Primary node and provides fault tolerance in case the Primary node fails.

- The Primary node in the database cluster is responsible for handling write operations and ensuring data consistency. The Replica node(s) replicate data from the Primary node and can be used for read operations, reducing the load on the Primary node and improving scalability.

## Issues with this Infrastructure

While this three-server web infrastructure provides improved scalability and availability compared to the one-server setup, there are still some issues to consider:

1. **Single Points of Failure**: Although there are multiple servers, each component is still hosted on a single server. If any of the servers (e.g., Server 1 or Server 2) experience hardware failure or other issues, the corresponding functionality becomes unavailable until the server is repaired. The load balancer itself can also be a single point of failure.

2. **Security Concerns**: The infrastructure lacks certain security measures, such as a firewall and HTTPS (SSL/TLS) encryption. Without a firewall, the servers may be exposed to potential attacks or unauthorized access. The absence of HTTPS leaves the communication between the website and users unencrypted, potentially compromising sensitive data.

3. **Monitoring**: The infrastructure does not include a monitoring system to track server performance, resource usage, or application health. Monitoring is crucial for proactive issue detection, capacity planning, and ensuring the overall reliability and performance of the infrastructure.

To address these issues, additional measures should be considered, including implementing redundancy for critical components, introducing security measures like firewalls and HTTPS, and setting up a comprehensive monitoring system to monitor the health and performance of the servers, load balancer, and database cluster.
