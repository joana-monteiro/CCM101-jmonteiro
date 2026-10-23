# Checkpoint 2 – Research: Multi-Tier Architecture

Before proceeding with the deployment, it is essential to understand the concept of multi-tier architecture and how it helps structure an application. This research explores the two-tier architecture, describes the functions of each tier, and explains how separating the web application and database into different containers improves organization, security, and maintainability.

---

## What Is a Two-Tier Architecture?

A **Two-Tier Architecture** is a system design that divides an application into two primary components: the application tier and the database tier. Both components work together to handle user requests and manage application data.

In this project, **Nextcloud** functions as the web application, while **MariaDB** serves as the database management system. Docker Compose allows the two containers to communicate within the same application environment.

This design organizes services according to their responsibilities, making the system easier to configure, maintain, and troubleshoot.

### How It Works

1. **User:** Accesses Nextcloud using a web browser.
2. **Nextcloud:** Receives the request and performs the necessary application processes.
3. **MariaDB:** Stores, retrieves, or updates the required database records.
4. **Response:** Nextcloud sends the requested information back to the user's browser.

---

## The Web / Application Tier

The Web/Application Tier is the part of the system that users access through their browsers. It provides the user interface and handles incoming requests.

For this deployment, **Nextcloud** serves as the application tier and can be accessed through port `8080`. It provides features such as the login interface, file management, and other application functions.

Nextcloud connects to MariaDB whenever it needs to retrieve or modify database records. It also relies on persistent storage to preserve uploaded files and other application data across container restarts.

**Key responsibilities:**

- Displays the application's interface to users.
- Receives and processes HTTP requests.
- Provides application features, including file management.
- Communicates with the database to access the information it needs.

This tier can be compared to a receptionist who assists visitors and coordinates with other departments to obtain the information they need.

---

## The Database Tier

The Database Tier manages the structured information required by the application. It organizes, stores, and retrieves records whenever the application requests them.

In this project, **MariaDB** acts as the database server. It stores information such as user accounts, file metadata, access permissions, and other application-related records. The actual contents of uploaded files are generally stored separately in Nextcloud's file storage.

MariaDB runs in its own container and communicates with Nextcloud through a Docker network. Direct public access to the database should be avoided, and connections should be limited to authorized services.

**Key responsibilities:**

- Stores and retrieves application records.
- Executes database queries and processes updates.
- Restricts access to authorized services and users.
- Maintains data consistency and integrity.

This tier can be compared to a secure records room where information is organized and accessed only by authorized personnel.

---

## Why Separate the Web Application and Database?

Running Nextcloud and MariaDB in separate containers provides several advantages compared with placing both services inside a single container.

### Main Benefits

- **Better Organization:** Each container performs a specific function, making the system easier to understand and manage.
- **Simplified Maintenance:** The application and database can be configured, updated, and troubleshot independently, provided their versions remain compatible.
- **Scalability:** Resources can be assigned to each service according to its requirements. Additional application instances may also be deployed when necessary.
- **Enhanced Security:** The database can operate on a private Docker network without being directly accessible from the public internet.
- **Improved Recovery:** Services can be restarted independently, while persistent volumes help preserve data when containers are replaced.
- **Portability:** Docker Compose simplifies the process of defining and reproducing the application environment on other compatible systems.

However, separating services does not automatically ensure complete security or eliminate the risk of data loss. Proper network configuration, access restrictions, persistent storage, and regular backups are still essential.

### Personal Reflection

Through this research, I learned that running an entire application inside a single container may seem convenient, but separating the application and database provides a more organized and manageable approach. Each service can focus on its assigned responsibilities, while Docker Compose simplifies communication between them.

I also realized that this architecture is useful for building applications that are easier to maintain, secure, and expand. Understanding how these components work together provides a strong foundation for deploying and managing containerized applications in real-world environments.
