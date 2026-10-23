# Checkpoint 6 – Technical Documentation: Docker Compose Guide

## Introduction

This guide documents the process of creating and configuring the `docker-compose.yml` file to deploy a two-tier application using **Nextcloud** and **MariaDB**.

Docker Compose makes it possible to define and manage multiple containers through a single YAML configuration file. In this activity, Nextcloud functions as the web application, while MariaDB manages the database information required by the system.

---

## 1. Creating the `docker-compose.yml` File

I started by creating a project directory named `nextcloud-deployment` in the KillerCoda Ubuntu Playground. Inside the directory, I used the `nano` text editor to create and edit the `docker-compose.yml` file.

### Commands Used

```bash
mkdir nextcloud-deployment
cd nextcloud-deployment
nano docker-compose.yml
```

**Explanation:**

- `mkdir` creates a new directory for the project.
- `cd` navigates into the newly created directory.
- `nano` opens a text editor for writing and modifying the Docker Compose configuration.

### Docker Compose Configuration

The following YAML configuration defines the Nextcloud application and MariaDB database services.

```yaml
version: '3'

services:
  database:
    image: mariadb:10.6
    environment:
      - MYSQL_ROOT_PASSWORD=cloudnova_root
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user

  app:
    image: nextcloud
    ports:
      - 8080:80
    environment:
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user
      - MYSQL_HOST=database
```

### Verifying the Configuration File

After saving the configuration, I executed the `cat` command to display the contents of the file and verify its structure.

```bash
cat docker-compose.yml
```

**Explanation:** The command prints the saved configuration in the terminal. Correct YAML formatting and indentation are essential because they determine how the configuration settings are organized and interpreted.

---

## 2. Understanding the Services

The `services:` section identifies the containers required to run the application. In this configuration, two services are defined.

| Service | Docker Image | Purpose |
|---|---|---|
| `database` | `mariadb:10.6` | Stores Nextcloud database records, including user information and file metadata. |
| `app` | `nextcloud` | Runs the web application and provides its user interface and file management features. |

Defining both services in the same Compose file simplifies deployment because Docker Compose can create and manage the containers as part of one project.

---

## 3. Connecting Nextcloud to MariaDB

Nextcloud uses the following environment variable to identify its database service:

```yaml
MYSQL_HOST=database
```

The value `database` matches the MariaDB service name defined in the Compose file. Docker Compose creates a default network for the services, allowing Nextcloud to locate MariaDB through Docker's internal DNS without requiring a manually assigned IP address.

### Understanding the Environment Variables

| Variable | Description |
|---|---|
| `MYSQL_ROOT_PASSWORD` | Defines the password for the MariaDB root account during database initialization. |
| `MYSQL_PASSWORD` | Specifies the password for the Nextcloud database user. |
| `MYSQL_DATABASE` | Identifies the database name, `nextcloud_db`. |
| `MYSQL_USER` | Defines the database username, `nextcloud_user`. |
| `MYSQL_HOST` | Specifies the database service that Nextcloud connects to. |

### Understanding Port Mapping

```yaml
ports:
  - 8080:80
```

This setting maps port `8080` on the host machine to port `80` inside the Nextcloud container.

Through the exposed port, I can access the Nextcloud web interface using the appropriate URL provided by the KillerCoda environment.

The MariaDB service does not define a `ports:` mapping. As a result, its database port is not published directly to the host through this configuration, and the application can communicate with it through the internal Docker network.

During deployment, the Nextcloud setup page displayed an **"Autoconfig file detected"** message. This indicated that the application had detected an automatic configuration file.

---

## 4. Comparing `docker run` and `docker-compose up -d`

Docker offers different methods for creating and running containers. The following table highlights the main differences between the two approaches.

| Aspect | `docker run` | `docker-compose up -d` |
|---|---|---|
| Container management | Starts an individual container through a command. | Starts the services defined in the Compose configuration. |
| Networking | Network settings may need to be configured manually. | Automatically creates and manages the default project network. |
| Reusability | Container settings must be supplied again when needed. | Reuses the saved YAML configuration. |
| Cleanup | Containers can be stopped and removed individually. | Project services and the default network can be removed together. |

**Simple explanation:** Using `docker run` involves configuring and starting containers individually, whereas Docker Compose uses a shared configuration file to manage the application as a whole.

This approach demonstrates the concept of **Infrastructure as Code (IaC)**, in which infrastructure settings are documented in configuration files that can be reused instead of recreated manually.

The `-d` option enables detached mode, allowing containers to run in the background while the terminal remains available for additional commands.

---

## 5. Deploying and Verifying the Application

Once the configuration file was ready, I executed the following command to launch the application services.

```bash
docker-compose up -d
```

**Explanation:** This command creates and starts the containers defined in the Compose file. The `-d` option allows them to operate in the background.

### Checking Container Status

To verify whether the services were running, I used the following command:

```bash
docker-compose ps
```

This command displays the Compose services, their container status, and relevant port information.

During verification, both the Nextcloud application and MariaDB containers displayed an `Up` status.

The output included the following port information:

- **Nextcloud:** `0.0.0.0:8080->80/tcp`
- **MariaDB:** `3306/tcp`

The Nextcloud mapping indicates that port `8080` is published on the host and forwarded to port `80` inside the container. The MariaDB entry indicates that the container listens on port `3306`, but this configuration does not publish that port to the host.

These results confirmed that both containers were running and that the Nextcloud application port was configured. Additional testing through the browser and database connection checks can provide further confirmation that the application is functioning correctly.

---

## 6. Stopping and Removing the Deployment

After completing the verification process, I used the following command to stop and remove the deployment.

```bash
docker-compose down
```

**Explanation:** This command stops and removes the containers associated with the Compose project and removes the default project network.

Named volumes are not normally removed by this command. However, the current configuration does not explicitly define persistent volumes for Nextcloud or MariaDB. Therefore, important application files and database records should be stored in properly configured persistent volumes before using this deployment beyond basic testing.

---

## 7. Learning Outcomes

Through this activity, I developed an understanding of how to:

- Create a Docker Compose configuration file using the Linux terminal.
- Define a two-tier application architecture using Nextcloud and MariaDB.
- Establish communication between application and database containers through an internal Docker network.
- Configure port mapping to make a web application accessible.
- Deploy and inspect multiple containers using Docker Compose commands.
- Stop and remove containers and networks after testing.
- Apply Infrastructure as Code principles by defining deployment settings in a reusable YAML file.

## Conclusion

This activity helped me understand how Docker Compose simplifies the deployment and management of applications that require multiple containers. By defining Nextcloud and MariaDB in a single configuration file, I was able to manage both services using a small set of commands.

I also gained practical knowledge of environment variables, service discovery, port mapping, YAML formatting, and container lifecycle management. These concepts provide a foundation for developing more organized, maintainable, and reliable cloud application deployments.
