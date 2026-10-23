# 🐳☁️ Laboratory 6: The Cloud Deployment Engineer

<br>

## 🎯 Mission Overview

Congratulations! Your flawless work in deploying data storage solutions has earned you a spot on the Cloud Deployment Team at CloudNova Technologies.

Up until now, you have been deploying single containers (like a standalone web server or a storage bucket). However, real-world enterprise applications are rarely just one container. They are "multi-tier" systems that require a frontend web application communicating seamlessly with a backend database. Deploying these one by one manually is prone to error.

Enter Docker Compose. In this mission, you will transition from manual commands to Infrastructure as Code (IaC). Using a YAML configuration file, you will define a multi-container private cloud storage application (Nextcloud and MariaDB) and deploy the entire stack simultaneously with a single command!

> Remember: A junior engineer deploys servers by typing commands; a senior engineer deploys infrastructure by writing code.

<br>

## 📋 Objectives

At the end of this laboratory activity, you should be able to:

- Explain the concept of a multi-tier application architecture.
- Understand the purpose and structure of a docker-compose.yml file.
- Use a Linux command-line text editor (nano) to create configuration files.
- Deploy a multi-container application (Nextcloud + Database) using Docker Compose.
- Document deployment procedures and Infrastructure as Code (IaC) principles using Markdown.
- Continue expanding your professional GitHub Cloud Computing Portfolio.

---

## Commands Executed

The following commands were used to configure, deploy, verify, and remove the application services.

| Command | Description |
|---|---|
| `mkdir nextcloud-deployment` | Creates a directory for the deployment project. |
| `cd nextcloud-deployment` | Navigates to the project directory. |
| `nano docker-compose.yml` | Opens the text editor to create or edit the configuration file. |
| `cat docker-compose.yml` | Displays the configuration file for verification. |
| `docker-compose up -d` | Creates and starts the defined services in the background. |
| `docker-compose ps` | Displays the current status of the containers. |
| `docker-compose down` | Stops and removes the containers and the default project network. |

---

## Application Architecture

The deployment uses a two-tier architecture consisting of a web application and a database service.

```text
             USER
               |
               v
          WEB BROWSER
               |
          Port 8080
               |
               v
     +---------------------+
     |    NEXTCLOUD APP    |
     |    Service: app     |
     +---------------------+
               |
       Private Docker Network
               |
               v
     +---------------------+
     |       MARIADB       |
     |  Service: database  |
     +---------------------+
               |
          Port 3306
        Internal Network
```

**How the architecture operates:**

- **Web tier:** Nextcloud provides the user interface and processes application requests.
- **Database tier:** MariaDB stores the structured information required by Nextcloud.
- **Container networking:** Docker Compose enables Nextcloud to communicate with MariaDB through the service name `database`.
- **Port configuration:** Nextcloud is accessible through the host's published port `8080`, while MariaDB is not directly exposed through a host-published port.

---

## Deployment Evidence

This section documents the main stages of the laboratory activity. The corresponding screenshots can be inserted in the spaces provided below.

### 1. Creating the Configuration File

I used the `nano` text editor to create and configure the `docker-compose.yml` file containing the Nextcloud and MariaDB service definitions.

**Figure 1.** Creating the Docker Compose configuration using the nano editor.

### 2. Verifying the Configuration

After saving the file, I used the `cat` command to review its contents and check whether the YAML structure and indentation were correct.

**Figure 2.** Inspecting the saved configuration in the terminal.

### 3. Deploying the Containers

I executed `docker-compose up -d` to start the application services and used `docker-compose ps` to check the status of the containers.

**Figure 3.** Starting the services and verifying their container status.

### 4. Accessing the Nextcloud Interface

After deployment, I opened the Nextcloud setup page through the configured web port to verify that the application interface was accessible.

**Figure 4.** Accessing the Nextcloud setup page through port 8080.

### 5. Removing the Deployment

After completing the verification process, I ran `docker-compose down` to stop and remove the containers and the default network created for the project.

**Figure 5.** Stopping and removing the deployed containers and network.

---

## Skills and Knowledge Acquired

| Skill | Learning Outcome |
|---|---|
| Docker Compose | Learned to manage multiple containers using a shared configuration file. |
| YAML | Practiced creating configuration files with proper formatting and indentation. |
| Application Deployment | Learned to start, inspect, and remove containerized services. |
| Container Networking | Understood how services communicate using Docker Compose service names. |
| Security | Learned the importance of restricting database exposure and protecting credentials. |
| Troubleshooting | Practiced checking container status and verifying application accessibility. |
| Technical Documentation | Improved my ability to document deployment procedures and supporting evidence using Markdown. |

---

## Mission Status

**Completed activities:** Docker Compose configuration, multi-container deployment, application accessibility verification, container cleanup, and technical documentation.

*Cloud Computing Laboratory 6 — Developing practical skills in infrastructure automation, container management, and cloud application deployment.*
