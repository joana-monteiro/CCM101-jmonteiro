# Checkpoint 4 - Cloud Platform Recommendation Challenge

This activity compares different cloud platforms according to the specific needs of various organizations. Each client is assigned a cloud provider based on factors such as budget, technology requirements, scalability, and business objectives.

---

## Client A – Startup Company

### Scenario

> A startup company is preparing to launch a new mobile application. The company has a limited budget but expects its user base and business activities to increase significantly in the future.

### Recommendation

| **Requirement**                | **Answer**                                                                                                                                                                                                                                                                                                        |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Recommended Cloud Platform** | **Google Cloud Platform (GCP)**                                                                                                                                                                                                                                                                                   |
| **Recommendation**             | GCP is a suitable choice for the startup because the company can begin with a smaller amount of cloud resources and increase them as the application attracts more users. This can reduce the need for costly physical hardware while providing useful services for developing and deploying mobile applications. |
| **Service 1**                  | **Firebase** – Provides tools and services that support the development, testing, and management of mobile applications.                                                                                                                                                                                          |
| **Service 2**                  | **Cloud Run** – Allows applications to run in the cloud without requiring the company to manage physical servers.                                                                                                                                                                                                 |
| **Service 3**                  | **Cloud Storage** – Provides storage for application files, images, videos, and other types of data.                                                                                                                                                                                                              |
| **Service 4**                  | **Cloud SQL** – Offers a managed relational database for storing and managing application information.                                                                                                                                                                                                            |

---

## Client B – University

### Scenario

> A university currently uses Windows Server, Microsoft 365, and Active Directory. The institution wants to move some of its existing services and systems to cloud-based infrastructure.

### Recommendation

| **Requirement**                | **Answer**                                                                                                                                                                                                                                                                     |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Recommended Cloud Platform** | **Microsoft Azure**                                                                                                                                                                                                                                                            |
| **Recommendation**             | Azure is an appropriate choice because the university already relies on Microsoft technologies. Azure provides compatibility with Windows Server, Microsoft 365, and Microsoft Entra ID, which can make the transition to cloud services more convenient and easier to manage. |
| **Service 1**                  | **Azure Virtual Machines** – Allows Windows Server applications and workloads to operate in a cloud environment.                                                                                                                                                               |
| **Service 2**                  | **Microsoft Entra ID** – Provides identity management, authentication, and access control for users and resources.                                                                                                                                                             |
| **Service 3**                  | **Azure App Service** – Provides a platform for hosting websites and web applications.                                                                                                                                                                                         |
| **Service 4**                  | **Azure Storage** – Provides storage for documents, files, backups, and other digital information.                                                                                                                                                                             |

---

## Client C – AI Research Company

### Scenario

> A research organization develops Artificial Intelligence and Machine Learning applications that require powerful computing resources for data processing and model training.

### Recommendation

| **Requirement**                | **Answer**                                                                                                                                                                                                                                                                                                        |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Recommended Cloud Platform** | **Google Cloud Platform (GCP)**                                                                                                                                                                                                                                                                                   |
| **Recommendation**             | GCP is a strong option for AI research because it provides specialized computing resources for Artificial Intelligence and Machine Learning workloads. Its GPU and TPU technologies can help accelerate model training, while its AI services support the development and deployment of intelligent applications. |
| **Service 1**                  | **Vertex AI** – Provides tools for creating, training, evaluating, and deploying artificial intelligence models.                                                                                                                                                                                                  |
| **Service 2**                  | **Compute Engine** – Provides customizable virtual machines for handling resource-intensive computing tasks.                                                                                                                                                                                                      |
| **Service 3**                  | **Cloud TPU** – Provides specialized processors designed to support Artificial Intelligence and Machine Learning workloads.                                                                                                                                                                                       |
| **Service 4**                  | **Google Kubernetes Engine (GKE)** – Provides a managed platform for deploying and scaling applications that use containers.                                                                                                                                                                                      |

---

## Client D – Global E-Commerce Company

### Scenario

> A multinational e-commerce company serves customers in different parts of the world. It needs a dependable cloud infrastructure that can remain available during periods of heavy traffic and automatically respond to changes in demand.

### Recommendation

| **Requirement**                | **Answer**                                                                                                                                                                                                                                                                 |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Recommended Cloud Platform** | **Amazon Web Services (AWS)**                                                                                                                                                                                                                                              |
| **Recommendation**             | AWS is a suitable choice because its extensive global infrastructure can support customers in different regions. Its scaling and load-balancing capabilities allow an online store to handle traffic increases while maintaining application availability and performance. |
| **Service 1**                  | **Amazon EC2** – Provides scalable virtual servers for hosting applications and websites.                                                                                                                                                                                  |
| **Service 2**                  | **EC2 Auto Scaling** – Automatically adjusts computing resources based on changes in application demand.                                                                                                                                                                   |
| **Service 3**                  | **Elastic Load Balancing** – Distributes incoming traffic across multiple servers to improve application reliability and availability.                                                                                                                                     |
| **Service 4**                  | **Amazon CloudFront** – Delivers website content efficiently to users located around the world.                                                                                                                                                                            |
| **Service 5**                  | **Amazon RDS** – Provides a managed database service for storing and managing application information.                                                                                                                                                                     |

---

# Summary of Checkpoint 4

The following table shows the recommended cloud provider for each client based on their main business and technical requirements.

| **Client**                 | **Recommended Platform**        | **Main Reason**                                                                           |
| -------------------------- | ------------------------------- | ----------------------------------------------------------------------------------------- |
| **Client A – Startup**     | **Google Cloud Platform (GCP)** | Flexible resources that allow the company to start small and scale as the business grows. |
| **Client B – University**  | **Microsoft Azure**             | Strong compatibility with the university's existing Microsoft technologies.               |
| **Client C – AI Research** | **Google Cloud Platform (GCP)** | Advanced AI and Machine Learning services with high-performance computing capabilities.   |
| **Client D – E-Commerce**  | **Amazon Web Services (AWS)**   | Global infrastructure with strong scalability and availability features.                  |

---

# Checkpoint 6 - Multi-Cloud Decision Matrix

This decision matrix identifies the cloud provider that is most appropriate for different organizational and technical requirements.

| **Business Requirement**    | **Recommended Platform**        | **Justification**                                                                                                                                           |
| --------------------------- | ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Startup Company**         | **Google Cloud Platform (GCP)** | GCP offers scalable and flexible services that allow startups to begin with limited resources and expand as their business develops.                        |
| **Enterprise Organization** | **Amazon Web Services (AWS)**   | AWS provides a wide range of cloud services, security features, and global infrastructure that can support the needs of large organizations.                |
| **Microsoft Environment**   | **Microsoft Azure**             | Azure integrates effectively with Windows Server, Microsoft 365, and Microsoft Entra ID, making it suitable for organizations using Microsoft technologies. |
| **AI / Machine Learning**   | **Google Cloud Platform (GCP)** | GCP provides AI-focused services such as Vertex AI and specialized computing resources for Machine Learning workloads.                                      |
| **Kubernetes Deployment**   | **Google Cloud Platform (GCP)** | Google Kubernetes Engine (GKE) provides a managed Kubernetes environment for deploying and scaling container-based applications.                            |
| **Global Web Application**  | **Amazon Web Services (AWS)**   | AWS provides global infrastructure, load balancing, content delivery, and automatic scaling for applications serving users internationally.                 |

---

# Summary

Each major cloud provider offers different strengths, making each platform more appropriate for particular organizations and workloads.

| **Cloud Provider**              | **Best Suited For**                                                                                     |
| ------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Amazon Web Services (AWS)**   | Enterprise organizations and applications that operate on a global scale.                               |
| **Microsoft Azure**             | Organizations that primarily use Microsoft-based technologies and services.                             |
| **Google Cloud Platform (GCP)** | Startups, Artificial Intelligence and Machine Learning workloads, and applications based on Kubernetes. |

### Overall Recommendation

* **AWS** → Best suited for **large enterprises and globally distributed applications**
* **Azure** → Best suited for **organizations that rely heavily on Microsoft technologies**
* **GCP** → Best suited for **startups, AI/ML workloads, and Kubernetes-based applications**
