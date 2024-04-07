# Customer Medical Records Diagnosis


## Company Overview

The "Customer Medical Records Diagnosis" project is developed by a healthcare organization aiming to provide patients with concise and understandable summaries of their medical reports. This three-tier web application leverages AWS services to securely store, process, and deliver patient data and medical analyses.

![Customer Medical Report Analysis Sample Architectures](https://github.com/ComputersAviSR/Cloud-Computing/blob/main/Solution%20Architectures/AWS_Architectures/Customer%20Medical%20Report%20Diagnosis/Medical_diagnosis_ha.jpg)

## Use Case

Patients often receive detailed medical reports that can be complex to interpret. This project aims to simplify the process by extracting key information from PDF reports, analyzing them using AWS Comprehend Medical, and then sending summarized reports directly to patients via email.

## AWS Services Utilized

AWS offers a suite of services that enable scalable, secure, and efficient healthcare applications:

- **Amazon S3**: Used to store patient-uploaded PDF documents securely.
- **Amazon Aurora MySQL**: Global database for storing customer data such as login information and signup details.
- **Amazon ElastiCache (Redis)**: Manages session data to optimize user login experiences.
- **AWS Comprehend Medical**: Utilized to extract and analyze medical information from PDF reports.
- **Amazon SNS (Simple Notification Service)**: Triggers email notifications to patients when their medical report summaries are ready.
- **AWS Lambda**: Handles event-driven processing, such as triggering analysis by Comprehend Medical.
- **AWS Route 53**: Manages domain name resolution to direct user requests to the application.
- **Amazon CloudFront**: Content delivery network (CDN) for faster content delivery to users.
- **Application Load Balancer (ALB)**: Distributes incoming traffic to EC2 instances based on health checks and load.

## Architecture Overview

The architecture of the "Customer Medical Records Diagnosis" project is designed to be scalable, fault-tolerant, and efficient:

1. **User Interaction**:
   - Users interact with the application via a web interface, uploading PDF reports and accessing their summaries.

2. **Data Storage**:
   - Patient-uploaded PDF documents are stored securely in Amazon S3.
   - Customer data such as login information and signup details are stored in Amazon Aurora MySQL.

3. **Session Management**:
   - Amazon ElastiCache (Redis) manages session data to maintain login state and improve user experience.

4. **Document Analysis**:
   - AWS Comprehend Medical processes uploaded PDF documents, extracting key medical information.

5. **Notification and Delivery**:
   - When analysis is complete, Amazon SNS triggers email notifications to patients with links to their summarized reports in Amazon S3.

6. **Application Delivery**:
   - AWS Route 53 resolves user requests to the application, directing traffic to Amazon CloudFront for optimized content delivery and then to the ALB.

## Service Responsibilities

- **ALB (Application Load Balancer)**:
  - Ensures high availability and fault tolerance by distributing incoming traffic among healthy EC2 instances.
  
- **Amazon S3**:
  - Securely stores patient-uploaded PDF documents and final summarized reports.
  
- **AWS Comprehend Medical**:
  - Analyzes medical information extracted from PDF reports to generate patient summaries.
  
- **Amazon Aurora MySQL**:
  - Global database for storing customer data, ensuring data consistency and availability across regions.
  
- **Amazon ElastiCache (Redis)**:
  - Manages session data to optimize login state and enhance user experience.
  
- **Amazon SNS**:
  - Triggers email notifications to patients when their medical report summaries are ready.
  
- **AWS Lambda**:
  - Executes event-driven tasks, such as triggering analysis by Comprehend Medical in response to S3 events.
  
- **AWS Route 53 and CloudFront**:
  - Manages domain name resolution and optimizes content delivery for improved application performance.
