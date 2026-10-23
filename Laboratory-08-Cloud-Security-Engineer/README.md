
# Laboratory 08 — The Cloud Security Engineer

## Mission Overview

This laboratory activity focuses on protecting a Linux server using UFW (Uncomplicated Firewall). The tasks include deploying an Nginx web application, examining firewall rules, applying a Default Deny policy, and permitting only the network services necessary for the application to operate.

## Objectives

- Understand the Principle of Least Privilege and its role in server security.
- Recognize the potential attack surface of a virtual machine.
- Examine the server's existing network access settings.
- Apply a Default Deny policy using UFW.
- Permit SSH connections for remote server administration.
- Allow TCP traffic on port 8080 for the web application.
- Record the configuration process and organize the results in a professional GitHub portfolio.

## Tools and Technologies

- Ubuntu Linux
- Docker
- Nginx Web Server
- UFW Firewall
- cURL
- Markdown
- GitHub

## Commands Executed

| Command | Purpose |
|---|---|
| `docker --version` | Verifies that Docker is installed and available. |
| `docker ps` | Displays the currently running containers. |
| `curl -i http://localhost:8080` | Checks the accessibility of the locally hosted web application. |
| `sudo ufw allow ssh` | Creates a rule permitting SSH connections. |
| `sudo ufw default deny incoming` | Sets incoming network traffic to be denied by default. |
| `sudo ufw default allow outgoing` | Allows outgoing network connections by default. |
| `sudo ufw enable` | Activates the UFW firewall. |
| `sudo ufw status verbose` | Displays the firewall's current status, policies, and rules. |
| `sudo ufw allow 8080/tcp` | Permits incoming TCP connections on port 8080. |
| `sudo ufw status numbered` | Lists firewall rules with their corresponding numbers. |

## Screenshots and Evidence

| Evidence File | Description |
|---|---|
| `vulnerable-app-running.png` | Captures the running Nginx container and a successful HTTP response. |
| `firewall-activated.png` | Shows the enabled UFW firewall and its default policies. |
| `firewall-port-allowed.png` | Displays the numbered firewall rules and the web application connectivity test. |

All screenshots are organized in the `screenshots/` directory for convenient access and review.

## Skills Acquired

- Applying fundamental server security practices.
- Establishing and managing host-based firewall rules.
- Controlling network access through specific ports.
- Deploying and testing applications running inside Docker containers.
- Preparing structured technical documentation using Markdown.
- Maintaining an organized GitHub repository for laboratory activities and project evidence.

## Mission Completion

The laboratory activity is considered complete once the firewall has been configured and its settings verified, the required documentation has been prepared, all three screenshots have been uploaded, and the changes have been committed to the GitHub repository.

**Note:** All documented results and screenshots must accurately reflect the commands executed and the actual output obtained in the laboratory environment.

