# Laboratory Activity 4 — Mission 4: The Cloud-Native Engineer

## Mission Overview

After completing the previous multi-cloud activities, I continued my role as a **Cloud-Native Engineer** at CloudNova Technologies.

This laboratory activity introduced the concept of **containerization** and its differences from traditional **Virtual Machines (VMs)**. Containers are widely used in modern cloud environments because they are lightweight, portable, resource-efficient, and capable of starting applications quickly.

Using the **KillerCoda Playground**, I explored the fundamental concepts of virtualization and containerization. I also practiced essential Docker commands and deployed a web server using an Nginx container.

> **Key Idea:** Traditional system administrators primarily focus on managing servers and infrastructure, while cloud-native engineers focus more on managing applications, services, and workloads within cloud environments.

---

## Objectives

At the end of this laboratory activity, I was able to:

* Explain the differences between Virtual Machines and containers.
* Use the Docker-enabled environment available through KillerCoda.
* Execute fundamental Docker Command Line Interface (CLI) commands.
* Download, create, run, monitor, stop, and remove an Nginx container.
* Document Docker procedures using structured Markdown formatting.
* Enhance my GitHub Cloud Computing Portfolio through technical documentation.

---

## Docker Commands Executed

The following Docker commands were performed throughout **Checkpoints 3, 4, and 5**.

### Checkpoint 3 — Verifying the Docker Installation

| Command            | Description                                                                                                                  |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| `docker --version` | Displays the currently installed Docker version.                                                                             |
| `docker info`      | Provides detailed information about the Docker environment, including containers, images, storage, and system configuration. |

**Result Observed:**

The Docker environment reported **Docker version 29.1.3** running on **Ubuntu 24.04.4 LTS**. Because the environment was newly initialized, there were initially **0 containers and 0 images**.

**Screenshot Description — Checkpoint 3.1:**
The terminal displayed the installed Docker version, confirming that Docker was properly installed and ready to be used.

**Screenshot Description — Checkpoint 3.2:**
The `docker info` command displayed detailed information about the Docker system, including the operating system, number of containers, number of images, and other configuration details.

---

### Checkpoint 4 — Deploying the First Container

For this checkpoint, I deployed an **Nginx web server** inside a Docker container.

| Command                                              | Description                                                                                                               |
| ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `docker pull nginx`                                  | Retrieves the official Nginx image from Docker Hub.                                                                       |
| `docker run -d -p 8080:80 --name server-nginx nginx` | Creates and starts an Nginx container named `server-nginx` in detached mode and maps host port 8080 to container port 80. |
| `curl http://localhost:8080`                         | Sends a request to the Nginx server to verify that the web server is running properly.                                    |

**Result Observed:**

The terminal returned the HTML content of the **Nginx Welcome Page**. This verified that the Nginx web server had been successfully deployed and was operating inside the **`server-nginx`** Docker container.

---

### Checkpoint 5 — Managing the Container Lifecycle

This checkpoint focused on the fundamental lifecycle operations of the **`server-nginx`** Docker container, including viewing, stopping, verifying, and removing the container.

| # | Command                    | Description                                                                                                                  |
| - | -------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 1 | `docker ps`                | Lists currently running containers and verifies that the `server-nginx` container is active.                                 |
| 2 | `docker stop server-nginx` | Stops the running `server-nginx` container.                                                                                  |
| 3 | `docker ps -a`             | Lists all containers, including stopped containers, and verifies that the `server-nginx` container has stopped successfully. |
| 4 | `docker rm server-nginx`   | Removes the stopped `server-nginx` container from the Docker environment.                                                    |
| 5 | `docker ps -a`             | Verifies that no containers remain in the environment.                                                                       |

---

## Skills Learned

Through this laboratory activity, I developed several practical skills related to cloud computing and containerization:

* **Virtualization and Containerization:** Developed an understanding of how containers differ from Virtual Machines in terms of performance, resource consumption, and deployment.
* **KillerCoda Playground:** Gained hands-on experience using a cloud-based environment for practicing Docker operations.
* **Docker CLI:** Learned how to use essential Docker commands for downloading images, creating containers, mapping ports, and inspecting the Docker environment.
* **Container Lifecycle Management:** Practiced creating, monitoring, stopping, and removing Docker containers.
* **Web Server Deployment:** Successfully deployed an Nginx web server using a Docker container named **`server-nginx`**.
* **Technical Documentation:** Improved my ability to document technical procedures using Markdown and GitHub.
* **Troubleshooting:** Learned how to use the **Traffic** feature in KillerCoda to access exposed ports when `localhost:8080` could not be reached directly.

---

## Challenges Encountered

One of the main challenges I encountered during this activity was becoming familiar with the different Docker commands and their functions. Initially, commands such as `docker run`, `docker ps`, `docker stop`, and `docker rm` were unfamiliar, which made managing and monitoring containers more difficult.

I addressed this challenge by:

* Carefully following the laboratory instructions.
* Practicing each Docker command in the **KillerCoda** environment.
* Reviewing and observing the output produced after executing each command.

Through repeated practice, I became more familiar with the purpose and proper usage of each command. I learned how Docker commands can be used to create, inspect, manage, stop, and remove containers.

> This experience improved my confidence in using the Docker command line and strengthened my understanding of basic container management.

---

## References

Amazon Web Services. (2025, December 8). *Containers vs. virtual machines: Understanding the difference*. AWS Builder Center.
https://builder.aws.com/content/2lngiMeN3ZNKY4AFS5ih5lGVGN0/containers-vs-virtual-machines-understanding-the-difference

CleanStart. (2026, June 9). *Containers vs. virtual machines: Architecture, security, and performance compared*.
https://www.cleanstart.com/knowledge-hub/containers-vs-virtual-machines

Docker. (n.d.). *Docker documentation*.
https://docs.docker.com/

KillerCoda. (n.d.). *KillerCoda playgrounds*.
https://killercoda.com/playgrounds
