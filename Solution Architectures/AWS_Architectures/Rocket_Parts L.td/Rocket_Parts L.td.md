# Project Rocket Part Procurement (A Fictional Company) 🚀

![Rocket Parts L.td Sample Architectures](https://github.com/ComputersAviSR/Cloud-Computing/blob/main/Solution%20Architectures/AWS_Architectures/Rocket_Parts%20L.td/car_catalog_ha.jpg)

Project Rocket Part Procurement is a three-tier web application aimed at providing a platform for customers to browse and purchase rocket parts and services. This project leverages AWS services to ensure scalability, reliability, and performance.

## Company Overview and Use Case

Rocket Parts Co. specializes in manufacturing and selling rocket components and related services. The web application allows customers to browse catalog items & place orders.

## AWS Services and Benefits

AWS provides a robust cloud infrastructure that enables scalability, high availability, and security for our web application:
- **Elastic Compute Cloud (EC2)**: Provides scalable compute capacity to host our web application.
- **Auto Scaling**: Dynamically adjusts the number of EC2 instances based on traffic demand.
- **Application Load Balancer (ALB)**: Distributes incoming traffic across multiple EC2 instances for optimal performance and availability.
- **Relational Database Service (RDS)**: Manages our MySQL database to store and retrieve rocket parts data efficiently.
- **ElastiCache (Redis)**: In-memory data store for caching frequently accessed data and managing user session information.

## Architecture Overview

The architecture of Project Rocket Part Procurement involves the following components:

- **AWS DNS (Route 53)**: Resolves domain names to IP addresses, enabling clients to access the web application via a user-friendly URL.
- **Amazon CloudFront**: Content delivery network (CDN) that accelerates content delivery by caching static assets and routing requests to the nearest edge location.
- **Application Load Balancer (ALB)**: Routes incoming HTTP/HTTPS traffic to the appropriate EC2 instances based on defined rules and health checks.
- **Amazon RDS (MySQL)**: Hosts the relational database to store and manage rocket parts data.
- **Amazon ElastiCache (Redis)**: Provides an in-memory caching layer to improve performance by reducing database load and managing session data.

## Architecture Components and Responsibilities

- **AWS DNS (Route 53)**:
  - Resolves user-friendly domain names (URLs) to IP addresses for clients.
  
- **Amazon CloudFront**:
  - Accelerates content delivery by caching static assets (images, CSS, JS) and reducing latency.
  - Routes requests to the nearest edge location for improved performance.

- **Application Load Balancer (ALB)**:
  - Distributes incoming HTTP/HTTPS traffic across EC2 instances.
  - Performs health checks on instances and directs traffic only to healthy instances.

- **Amazon RDS (MySQL)**:
  - Stores and manages data related to rocket parts, including inventory, specifications, and customer orders.
  
- **Amazon ElastiCache (Redis)**:
  - Provides an in-memory caching layer to store session data and frequently accessed information.
  - Improves application performance by reducing database load and response times.

## User Interaction Example

1. **User Accesses Website**:
   - The client accesses the Rocket Parts Co. website using a user-friendly URL (e.g., `https://rocketpartsco.com`).

2. **DNS Resolution**:
   - AWS Route 53 resolves the domain name `rocketpartsco.com` to the IP address associated with the CloudFront distribution.

3. **CloudFront Distribution**:
   - CloudFront serves cached content and forwards dynamic requests to the nearest edge location for optimal performance.

4. **Application Load Balancer (ALB)**:
   - ALB receives incoming requests and distributes them to healthy EC2 instances based on configured routing rules and health checks.

5. **Web Application Processing**:
   - EC2 instances host the web application, which interacts with the RDS database and ElastiCache (Redis) for data retrieval, processing, and caching.

6. **Database Interaction**:
   - User interactions, such as browsing catalog items, placing orders, and retrieving real-time data, involve querying the RDS database.

7. **Session Management with ElastiCache**:
   - ElastiCache (Redis) manages user session data and provides caching to improve responsiveness and scalability of the application.

This architecture ensures a scalable, reliable, and high-performance platform for Project Rocket Part Procurement, allowing customers to browse, purchase, and interact with rocket parts and services seamlessly.
