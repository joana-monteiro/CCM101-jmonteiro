# Cloud Infrastructure Blueprint

## Mission Overview

This laboratory activity was designed to build a basic understanding of **cloud infrastructure** and its essential components. Using the **KillerCoda Playground** and **Linux Terminal**, I explored a cloud-based Linux system, checked its available resources, identified important infrastructure components, and examined the services provided by leading cloud providers.

For the activity, I created a simple cloud infrastructure architecture for a fictional company named **ARK**. The design shows how users connect through the Internet and access different cloud resources, including networking, servers, and databases.

The laboratory also allowed me to gain practical experience in **technical documentation, Markdown, Git, and GitHub repository management**.

---

## Objectives

The primary goals of this laboratory activity were to:

* Identify and explain the main components of cloud infrastructure.
* Examine the hardware and software resources available in a Linux environment.
* Understand the differences between compute, storage, networking, and identity resources.
* Explain how cloud resources communicate and work together.
* Create clear and organized technical documentation using Markdown.
* Maintain and organize a Cloud Computing portfolio using GitHub.

---

## Cloud Infrastructure Components

The fictional company **ARK** uses a simple cloud infrastructure that includes users, Internet connectivity, networking, computing resources, and storage.

| **Component**           | **Description**                                                                              |
| ----------------------- | -------------------------------------------------------------------------------------------- |
| **Compute Resource**    | Provides the processing power needed to run applications, services, and other workloads.     |
| **Storage Resource**    | Provides space for saving files, databases, application data, and other digital information. |
| **Network**             | Allows users and cloud resources to communicate and exchange information.                    |
| **User**                | Represents a person or client who accesses and uses cloud-based applications or services.    |
| **Internet Connection** | Provides the connection between users and the cloud environment.                             |

### Basic Architecture

The infrastructure follows this simple structure:

```text
        USER
          |
          v
      INTERNET
          |
          v
    CLOUD NETWORK
       /       \
      v         v
   SERVER    DATABASE
```

The diagram provides a simple view of how the main cloud components are connected.

* **User** – The person who accesses and uses the application.
* **Internet** – Provides the connection between the user and the cloud.
* **Cloud Network** – Connects and manages communication between cloud resources.
* **Server** – Runs the application and handles user requests.
* **Database** – Stores the information and data needed by the application.

In simple terms, the **user connects to the cloud through the Internet**. The **server handles the user's requests**, while the **database stores the application's information**.

---

## Tools and Technologies Used

The following tools and technologies were used during the laboratory activity:

| **Tool / Technology**     | **Purpose**                                                                         |
| ------------------------- | ----------------------------------------------------------------------------------- |
| **Canva**                 | Used to design the cloud infrastructure architecture diagram.                       |
| **KillerCoda Playground** | Provided the cloud-based Linux environment used for the laboratory exercises.       |
| **Linux Terminal**        | Used to execute commands and examine system resources and configurations.           |
| **GitHub**                | Used to store, organize, manage, and track laboratory files.                        |
| **Markdown**              | Used to create structured and readable technical documentation.                     |
| **Web Browser**           | Used to access GitHub, cloud provider documentation, and other technical resources. |

---

## Linux Commands Executed

Various Linux commands were used to examine the cloud environment and collect system information.

| **Command**                  | **Purpose**                                                                    |
| ---------------------------- | ------------------------------------------------------------------------------ |
| `cat /etc/os-release`        | Shows information about the installed Linux distribution and operating system. |
| `uname -r`                   | Displays the current Linux kernel version.                                     |
| `lscpu \| grep "Model name"` | Shows information about the system processor.                                  |
| `lscpu \| grep "^CPU(s):"`   | Displays the number of available CPU processing units.                         |
| `free -h`                    | Shows memory usage and available RAM in a readable format.                     |
| `df -h`                      | Displays disk usage, available storage, and file system capacity.              |
| `findmnt`                    | Shows mounted file systems and their mount points.                             |
| `hostname`                   | Displays the name assigned to the Linux system.                                |
| `hostname -I`                | Displays the IP address assigned to the system.                                |
| `ip addr`                    | Displays network interfaces, IP addresses, and network configuration details.  |

Using these commands provided hands-on experience in checking the operating system, processor, memory, storage, hostname, and network settings of a cloud-based Linux environment.

---

## Skills and Knowledge Acquired

Throughout the laboratory activity, I developed and improved the following skills:

* Identifying the basic components of cloud infrastructure.
* Checking Linux server resources using terminal commands.
* Understanding how compute resources support cloud applications.
* Understanding the purpose of cloud storage.
* Learning how networking connects different cloud resources.
* Designing a simple cloud infrastructure architecture.
* Creating organized technical documentation with Markdown.
* Using Git and GitHub for version control and project management.
* Comparing services offered by major cloud providers.
* Organizing laboratory activities and files within a GitHub repository.
* Developing a better understanding of Linux in cloud computing.

---

## Challenges Encountered

One of the challenges I encountered was understanding how **compute, storage, networking, and Internet connectivity** work together within a cloud environment. I also had to become familiar with different Linux commands used to inspect system resources and configurations.

Another challenge was reviewing the documentation of **AWS, Microsoft Azure, and Google Cloud**, because each provider has many services with different names, features, and capabilities.

Although these challenges required additional time and research, the activity helped improve my understanding of cloud infrastructure and strengthened my confidence in using Linux, researching cloud services, and creating technical documentation.

---

## Conclusion

This laboratory activity provided a practical introduction to **cloud infrastructure and its major components**. I learned how compute, storage, networking, and Internet connectivity work together to provide cloud-based services and resources.

The activity also improved my skills in **Linux system administration, cloud architecture, Markdown documentation, Git, and GitHub**. Designing the basic infrastructure for ARK helped me better understand how different cloud components communicate and support applications.

**Key Takeaway:** Cloud computing brings together **compute, storage, networking, and other resources** to provide accessible and reliable services through the Internet.
