# Checkpoint 7 - Linux Investigation and Cloud Migration

This checkpoint analyzes the specifications of a Linux server running in the **KillerCoda Ubuntu Playground** and evaluates whether the same server environment can be hosted on the three major cloud platforms: **Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP)**.

---

## 1. Linux Server Specifications

The following system information was obtained from the **KillerCoda Ubuntu Playground**. The environment operates as a virtualized **Ubuntu 24.04.4 LTS** server with limited computing resources.

| **Specification**    | **Details**                                   |
| -------------------- | --------------------------------------------- |
| **Operating System** | Ubuntu 24.04.4 LTS (Noble Numbat)             |
| **Distribution**     | Ubuntu                                        |
| **Version**          | 24.04                                         |
| **Architecture**     | x86_64                                        |
| **CPU**              | 1 CPU                                         |
| **CPU Model**        | Intel Xeon E312xx (Sandy Bridge, IBRS update) |
| **CPU Speed**        | 2.0 GHz                                       |
| **CPU Cores**        | 1 Core                                        |
| **CPU Threads**      | 1 Thread                                      |
| **Hypervisor**       | KVM                                           |
| **Virtualization**   | Full Virtualization                           |
| **RAM**              | 1.9 GiB                                       |
| **RAM Used**         | 410 MiB                                       |
| **RAM Available**    | 1.5 GiB                                       |
| **Swap Memory**      | 1.0 GiB                                       |
| **Disk Capacity**    | 19 GB                                         |
| **Disk Used**        | 5.4 GB                                        |
| **Disk Available**   | 13 GB                                         |
| **Disk Usage**       | 30%                                           |

### Server Overview

The Linux environment is a lightweight virtual machine configured with **1 CPU, 1.9 GiB of RAM, and 19 GB of disk storage**. These specifications provide a reference point for determining the minimum cloud resources required to recreate a similar server environment.

---

# 2. Cloud Services That Could Host the Server

The KillerCoda environment is based on a **virtualized Ubuntu 24.04.4 LTS server**. Since the three major cloud providers support Linux-based virtual machines, the same type of server environment can be deployed using **AWS, Microsoft Azure, or Google Cloud Platform**.

---

## AWS - Amazon EC2

### Amazon Elastic Compute Cloud (EC2)

| **Item**                 | **Details**                                                                                                                                                                                                               |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cloud Service**        | **Amazon EC2 (Elastic Compute Cloud)**                                                                                                                                                                                    |
| **Can Host the Server?** | **Yes**                                                                                                                                                                                                                   |
| **Why?**                 | Amazon EC2 supports Linux distributions, including Ubuntu. Users can select an appropriate EC2 instance with sufficient CPU and memory resources and configure storage that meets or exceeds the required 19 GB capacity. |
| **Suitable For**         | Ubuntu servers, websites, applications, development environments, and other Linux-based workloads.                                                                                                                        |
| **Conclusion**           | **Amazon EC2 can successfully recreate and host a similar Ubuntu server environment.**                                                                                                                                    |

---

## Microsoft Azure - Azure Virtual Machines

### Azure Virtual Machines

| **Item**                 | **Details**                                                                                                                                                                                                                                |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Cloud Service**        | **Azure Virtual Machines**                                                                                                                                                                                                                 |
| **Can Host the Server?** | **Yes**                                                                                                                                                                                                                                    |
| **Why?**                 | Azure Virtual Machines supports Ubuntu and other Linux distributions. Users can select a suitable virtual machine configuration with enough CPU and memory resources, while Azure managed disks can provide the required storage capacity. |
| **Suitable For**         | Ubuntu servers, websites, web applications, development environments, and other Linux-based services.                                                                                                                                      |
| **Conclusion**           | **Azure Virtual Machines can successfully recreate and host a similar Ubuntu server environment.**                                                                                                                                         |

---

## GCP - Compute Engine

### Google Compute Engine

| **Item**                 | **Details**                                                                                                                                                                                                                                                   |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cloud Service**        | **Google Compute Engine**                                                                                                                                                                                                                                     |
| **Can Host the Server?** | **Yes**                                                                                                                                                                                                                                                       |
| **Why?**                 | Google Compute Engine supports Ubuntu Linux and allows users to customize the resources assigned to virtual machines. A suitable configuration can provide the necessary CPU, RAM, and disk capacity required to reproduce the KillerCoda server environment. |
| **Suitable For**         | Ubuntu servers, websites, applications, development environments, and other Linux workloads.                                                                                                                                                                  |
| **Conclusion**           | **Google Compute Engine can successfully recreate and host a similar Ubuntu server environment.**                                                                                                                                                             |

---

# 3. Final Cloud Comparison

All three major cloud providers are capable of supporting the requirements of the KillerCoda Ubuntu server. Each platform provides virtual machine services that allow users to configure computing resources such as CPU, memory, storage, and operating systems according to their requirements.

| **Cloud Provider**  | **Cloud Service**      | **Ubuntu Support** | **Can Match Server Requirements?** |
| ------------------- | ---------------------- | ------------------ | ---------------------------------- |
| **AWS**             | Amazon EC2             | Yes                | Yes                                |
| **Microsoft Azure** | Azure Virtual Machines | Yes                | Yes                                |
| **GCP**             | Google Compute Engine  | Yes                | Yes                                |

---

## Final Conclusion

The **KillerCoda Ubuntu server can be successfully migrated or recreated on any of the three major cloud platforms**. AWS, Microsoft Azure, and Google Cloud all provide virtual machine services that support Ubuntu Linux and can be configured with resources comparable to those used by the original server environment.

The choice of cloud provider would therefore depend on additional factors such as pricing, existing organizational infrastructure, required services, scalability, security requirements, and the technical expertise available within the organization.

### Key Findings

* **AWS EC2** → Provides a flexible and scalable option for deploying and managing Linux-based servers.
* **Azure Virtual Machines** → A suitable choice for organizations that already use Microsoft technologies and services.
* **Google Compute Engine** → Provides customizable virtual machine configurations that are well suited for Linux environments and development workloads.
