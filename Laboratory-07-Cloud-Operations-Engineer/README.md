#  Laboratory 7: The Cloud Operations Engineer

##  Mission Overview

Congratulations! Your ability to deploy multi-tier architectures has proven your technical capabilities. You have now been promoted to the Cloud Operations Team (often referred to in the industry as Site Reliability Engineering, or SRE) at CloudNova Technologies.

Deploying a cloud application is only the first step; keeping it running smoothly is the real challenge. When a server crashes or a web page takes ten seconds to load, you cannot simply guess what is wrong. You must rely on Observability and Monitoring to see inside your infrastructure.

Using the KillerCoda Playground, you will step into the role of a Cloud Operations Engineer. You will establish a performance baseline for your Linux server, deploy a containerized application, generate artificial web traffic, and hunt down performance metrics and system logs to prove the application is healthy.

> Remember: A developer hopes the application works; a Site Reliability Engineer uses metrics and logs to prove it.


<br>

##  Objectives

At the end of this laboratory activity, you should be able to:

- Utilize native Linux command-line tools to monitor host CPU, Memory, and Disk capacity.
- Deploy a web container and track its real-time performance using Docker metrics.
- Generate web traffic and extract application access logs for analysis.
- Translate raw performance data into a readable technical report using Markdown.
- Continue expanding a professional GitHub Cloud Computing Portfolio.

<br>

## Monitoring Commands Executed

The following commands were executed to examine the Linux host, deploy the Nginx web server, generate test traffic, inspect application logs, and monitor container resource utilization.

| Command | Purpose |
| :--- | :--- |
| `free -h` | Checked the host machine's total, used, and available memory. |
| `df -h /` | Inspected the total capacity, used space, and remaining storage of the root filesystem. |
| `top` | Observed active processes, CPU utilization, and memory consumption. |
| `docker run -d --name client-website -p 8080:80 nginx` | Deployed the Nginx container in the background and connected host port 8080 to container port 80. |
| `curl http://localhost:8080` | Sent three HTTP requests to test normal website accessibility. |
| `curl http://localhost:8080/hidden-admin-page` | Accessed a nonexistent URL to verify the server's response to a missing page. |
| `docker logs client-website` | Examined the container logs for successful requests and missing-page errors. |
| `docker stats` | Monitored the container's real-time CPU, memory, and network utilization. |

---

## Laboratory Results and Observations

### 1. Host Memory Inspection

The `free -h` command displayed the server's total memory, used memory, free memory, and available RAM. The results provided an overview of the host's memory condition before and during the container deployment process.

### 2. Disk Storage Inspection

The `df -h /` command presented the root filesystem's total capacity, occupied space, and remaining storage. These measurements helped determine whether the server had sufficient disk space for its operating requirements.

### 3. CPU and Process Monitoring

The `top` command provided a continuously updated overview of active processes, CPU utilization, and memory usage. This information helped assess the server's current workload and identify processes that might consume significant system resources.

### 4. Nginx Container Deployment

The Docker command created and started the `client-website` container using the Nginx image. By forwarding host port 8080 to container port 80, the web server became accessible through `http://localhost:8080`.

### 5. Successful Website Access Tests

I used the `curl` command to send three HTTP requests to the web server, simulating ordinary website visits. The successful responses confirmed that Nginx was running and capable of handling basic HTTP requests.

### 6. Testing a Nonexistent Page

I accessed the `/hidden-admin-page` URL to examine how the server handled a request for an unavailable resource. Nginx returned a `404 Not Found` response, indicating that the requested page could not be located.

### 7. Application Log Analysis

The `docker logs client-website` command displayed the container's recorded output. By reviewing the logs, I could examine request activity and identify the missing-page request. This demonstrated how log analysis helps verify application behavior and investigate errors.

### 8. Container Performance Monitoring

The `docker stats` command displayed the container's live resource statistics, including CPU utilization, memory consumption, and network input/output. These measurements provided an overview of the container's resource usage while the Nginx web server was running.

---

## Skills Acquired

- **Server Resource Monitoring:** Developed the ability to inspect memory availability, disk capacity, CPU utilization, and active processes using Linux commands.
- **Docker Container Deployment:** Practiced running an Nginx web server inside a Docker container and configuring port mapping for website access.
- **Website Accessibility Testing:** Used `curl` to simulate website visits and examine responses to valid and nonexistent URLs.
- **Application Log Analysis:** Learned to review Docker logs to examine HTTP request activity and identify application errors.
- **Real-Time Container Monitoring:** Used `docker stats` to observe container CPU usage, memory consumption, and network activity.
- **Technical Documentation:** Improved my ability to organize command references, record observations, and present laboratory findings in a structured Markdown report.


