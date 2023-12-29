# Three-Server Secured Web Infrastructure with Monitoring

## Description
In this scenario, we will design a three-server web infrastructure to host the website www.foobar.com. The infrastructure aims to provide security, encrypted traffic (HTTPS), and monitoring capabilities. It consists of three servers, each with firewalls, an SSL certificate for HTTPS, and monitoring clients. This design enhances the security, privacy, and observability of the website.

## Infrastructure
The infrastructure includes the following components:

1. **Server 1**: This server hosts the web server (Nginx) responsible for handling HTTP requests and serving static content (HTML, CSS, JavaScript) to users. It is equipped with a firewall to protect against unauthorized access and malicious traffic.

2. **Server 2**: This server acts as the application server, running the server-side code of the website. It processes dynamic requests, interacts with the database, and generates HTML content. It also includes a firewall for added security.

3. **Server 3**: This server hosts the MySQL database, which stores and manages the website's data. It is equipped with a firewall to protect against unauthorized access attempts.

4. **Firewalls**: The firewalls are security devices that control and monitor incoming and outgoing network traffic. By adding firewalls to each server, we improve the overall security posture of the infrastructure. The firewalls can be configured to allow only necessary connections and filter out potentially harmful traffic.

5. **SSL Certificate**: An SSL certificate is added to enable HTTPS for the website. It encrypts traffic between the web server and users' browsers, ensuring data confidentiality and integrity. The certificate is obtained from a trusted certificate authority (CA) and installed on the web server to enable secure communication.

6. **Monitoring Clients**: Monitoring clients, such as data collectors for Sumo Logic or other monitoring services, are deployed on each server. These clients collect various performance and health metrics from the servers, including CPU usage, memory utilization, disk I/O, network traffic, and application-specific metrics. The collected data is sent to the monitoring service for analysis and alerting.

## Specifics of the Infrastructure

- Firewalls are added to each server to enhance security by controlling network traffic. They allow administrators to define rules to permit or deny specific types of connections based on protocols, ports, and IP addresses. Firewalls help protect against unauthorized access, malicious attacks, and potential data breaches.

- The SSL certificate is implemented to serve the website over HTTPS. HTTPS encrypts the communication between the web server and users' browsers, preventing eavesdropping, data tampering, and unauthorized access to sensitive information transmitted over the network.

- Monitoring is used to track the health, performance, and availability of the servers and the website. It helps identify and resolve issues proactively, ensures optimal performance, and provides insights for capacity planning and troubleshooting. Monitoring clients collect data from various system and application metrics and send it to a central monitoring service (e.g., Sumo Logic) for analysis and visualization.

- The monitoring tool collects data by deploying monitoring clients on each server. These clients collect metrics at regular intervals and send them to the monitoring service using specific protocols (e.g., HTTP, SNMP). The monitoring service then processes and stores the data, allowing administrators to view real-time and historical performance metrics, set up alerts, and generate reports.

- To monitor web server QPS (Queries Per Second), the monitoring tool can collect metrics such as the number of incoming requests per second or the number of queries processed by the web server. By analyzing these metrics, administrators can monitor the server's load, identify any spikes or anomalies in traffic, and take appropriate actions to optimize performance and ensure responsiveness.

## Issues with this Infrastructure

While this three-server secured web infrastructure provides improved security and monitoring capabilities, there are still some issues to consider:

1. **Terminating SSL at the Load Balancer**: Terminating SSL (decrypting HTTPS traffic) at the load balancer instead of the web server can be an issue. While it offloads the encryption workload from the web servers, it means the communication between the load balancer and web servers is in plain HTTP. This introduces a potential security vulnerability if the internal network is compromised.

2. **Single MySQL Server for Writes**: Having only one MySQL server capable of accepting writes can be a potential bottleneck and single point of failure. If the primary database server fails, write operations become unavailable until the server is restored. This can impact the availability and performance of the website.

3. **Identical Server Components**: Having servers with all the same components (database, web server, and application server) can be a problem in terms of resource allocation, scalability, and maintenance. If the website's requirements change, such as the need for more database capacity or additional application servers, scaling and managing resources can become challenging.

To address these issues, the following measures should be considered: implementing SSL termination at the web servers instead of the load balancer, introducing database replication for fault tolerance and read scaling, and designing a more modular and scalable infrastructure with separate# Three-Server Web Infrastructure with Load Balancer and Database Cluster

## Description
In this scenario, we will design a three-server web infrastructure to host the website www.foobar.com. The infrastructure will consist of two servers, a load balancer, a web server (Nginx), an application server, a MySQL database, and a set of application files. This design aims to improve the availability, scalability, and performance of the website compared to the previous one-server infrastructure.

## Infrastructure
The infrastructure includes the following components:

1. **Server 1**: This server hosts the web server (Nginx), which is responsible for handling HTTP requests and serving static content such as HTML, CSS, and JavaScript files. It receives requests for www.foobar.com and responds by sending the appropriate files to the user's browser.

2. **Server 2**: This server acts as the application server, running the server-side code of the website. It processes dynamic requests, interacts with the database, and generates HTML content to be served by the web server.

3. **Load Balancer**: The load balancer distributes incoming requests across multiple servers to ensure efficient resource utilization and high availability. It uses a distribution algorithm (e.g., round-robin, least connections) to determine which server should handle each request. The specific algorithm chosen should be based on the specific needs of the application.

4. **Application Files**: This set of files contains the codebase of the website's application. It includes server-side scripts, application logic, and any other necessary files to run the website's functionality.

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
