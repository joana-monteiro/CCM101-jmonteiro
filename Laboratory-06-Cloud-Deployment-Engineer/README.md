# Laboratory 6 — The Cloud Deployment Engineer

## Mission Overview

Laboratory Activity 6 focuses on deploying multi-container applications using Docker Compose and applying Infrastructure as Code (IaC) principles. The activity builds on previous container deployment exercises by introducing a more practical architecture in which a web application communicates with a separate database service.

During this laboratory, I configured a private cloud storage application using Nextcloud and MariaDB. Instead of managing each container individually, I used a `docker-compose.yml` file to define the application services, their configurations, and their communication requirements. Docker Compose was then used to deploy and manage the entire application stack through a single command.

This activity demonstrates how infrastructure configuration can simplify deployment, improve consistency, and reduce errors associated with manually managing multiple containers.

## Objectives

By completing this laboratory activity, I aimed to achieve the following objectives:

- Understand the structure and purpose of multi-tier application architecture.
- Explain the role of the `docker-compose.yml` file in defining application services.
- Create and edit configuration files using the Nano text editor in Linux.
- Deploy and manage a multi-container application using Docker Compose.
- Understand the fundamental principles of Infrastructure as Code (IaC).
- Document deployment procedures, configuration details, and verification results using Markdown.
- Expand my GitHub Cloud Computing Portfolio with technical documentation and laboratory evidence.

## Commands Executed

The following commands were used to prepare the project directory, configure the application, deploy the services, verify their status, and clean up the deployment.

| Command | Purpose |
|---|---|
| `mkdir nextcloud-deployment` | Creates a dedicated directory for the Nextcloud deployment project. |
| `cd nextcloud-deployment` | Changes the current working directory to the deployment project. |
| `nano docker-compose.yml` | Opens Nano to create or modify the Docker Compose configuration file. |
| `cat docker-compose.yml` | Displays the saved configuration for inspection and verification. |
| `docker-compose up -d` | Creates and starts the services defined in the configuration file in detached mode. |
| `docker-compose ps` | Displays the status of the containers associated with the deployment. |
| `docker-compose down` | Stops and removes the project's containers and default network. |

## Application Architecture

The application uses a two-tier architecture consisting of a web application layer and a database layer. These components operate in separate containers and communicate through a Docker network.

```text
                 USER
                   |
                   v
              WEB BROWSER
                   |
             Host Port 8080
                   |
                   v
       +------------------------+
       |      NEXTCLOUD         |
       |    Service: app        |
       |    Web Application     |
       +------------------------+
                   |
                   v
       +------------------------+
       |   PRIVATE DOCKER       |
       |       NETWORK          |
       +------------------------+
                   |
                   v
       +------------------------+
       |       MARIADB          |
       |  Service: database     |
       |     Database Layer     |
       +------------------------+
                   |
              Internal Port
                  3306
```

### Architecture Components

- **Web application layer:** Nextcloud provides the interface through which users access the cloud storage application and interact with its features.
- **Database layer:** MariaDB stores the structured application data required by Nextcloud.
- **Container networking:** Docker Compose connects the application services through a shared network, allowing Nextcloud to communicate with the database using the service name `database`.
- **Port configuration:** The Nextcloud service is accessible through host port `8080`. MariaDB uses its internal database port, `3306`, without requiring a host-published port.
- **Service isolation:** Separating the web application and database into individual containers improves organization and allows each service to be managed independently.

## Deployment Evidence

This section describes the major stages of the deployment process. Actual terminal screenshots should be inserted under the corresponding figure descriptions to provide evidence of the commands executed and their results.

### 1. Creating the Docker Compose Configuration

I created the `docker-compose.yml` file using the Nano text editor. The file defines the Nextcloud and MariaDB services, including their required configurations and deployment settings.

**Figure 1.** Creating the Docker Compose configuration file using Nano.

### 2. Reviewing the Configuration File

After editing and saving the configuration, I executed the `cat` command to inspect the file contents. This step helped me review the YAML structure, service definitions, and indentation before deploying the application.

**Figure 2.** Reviewing the saved Docker Compose configuration in the terminal.

### 3. Deploying and Verifying the Containers

I used `docker-compose up -d` to create and start the services in the background. After deployment, I executed `docker-compose ps` to examine the container status and determine whether the services were running as expected.

**Figure 3.** Deploying the application stack and checking the container status.

### 4. Accessing the Nextcloud Interface

Once the deployment was running, I accessed the Nextcloud setup page through the configured host port `8080`. This verification step helped confirm that the web application interface was reachable through the browser.

**Figure 4.** Accessing the Nextcloud setup interface through port 8080.

### 5. Cleaning Up the Deployment

After completing the deployment and accessibility checks, I executed `docker-compose down` to stop and remove the project containers and the default network. This step demonstrated how Docker Compose simplifies the removal of resources associated with a multi-container application.

**Figure 5.** Stopping and removing the deployed containers and project network.

## Skills and Knowledge Acquired

| Skill | Learning Outcome |
|---|---|
| Docker Compose | Learned how to define, deploy, and manage multiple containerized services through a single configuration file. |
| YAML Configuration | Practiced creating structured configuration files with correct syntax and indentation. |
| Application Deployment | Gained experience starting, inspecting, and removing containerized applications. |
| Container Networking | Understood how Docker Compose services communicate through service names within a shared network. |
| Security Practices | Learned the importance of limiting database exposure and protecting sensitive credentials. |
| Troubleshooting | Practiced examining container status and checking application accessibility to identify potential deployment issues. |
| Infrastructure as Code | Understood how declarative configuration files make infrastructure deployment more consistent and repeatable. |
| Technical Documentation | Improved my ability to prepare organized Markdown reports and document laboratory procedures with supporting evidence. |

## Mission Status

The laboratory activity covers the creation of the Docker Compose configuration, deployment of the Nextcloud and MariaDB containers, verification of application accessibility, cleanup of deployed resources, and preparation of technical documentation.

Successful completion should be supported by actual terminal output and screenshots confirming each relevant stage of the deployment process.

## Conclusion

Laboratory Activity 6 provided practical experience in deploying and managing a multi-container application using Docker Compose. Through the integration of Nextcloud and MariaDB, I gained a clearer understanding of how web applications and database services operate together within a containerized environment.

The activity also introduced the benefits of Infrastructure as Code, particularly the ability to define application configurations, deploy services consistently, and manage multiple containers efficiently. In addition, I learned the importance of container networking, database isolation, configuration validation, and deployment verification.

These skills will support my future cloud computing projects and strengthen my understanding of container orchestration concepts, infrastructure automation, and cloud application deployment.

*Cloud Computing Laboratory 6 — Building practical skills in Infrastructure as Code, container management, and multi-service application deployment.*
