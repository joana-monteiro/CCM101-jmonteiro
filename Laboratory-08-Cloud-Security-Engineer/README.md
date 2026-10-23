# Laboratory 08 — The Cloud Security Engineer

## Mission Overview

This laboratory activity focuses on securing a Linux server through UFW (Uncomplicated Firewall). The tasks involve running an Nginx web application, reviewing existing firewall configurations, implementing a Default Deny policy, and allowing only the network connections required for server administration and application access.

## Objectives

- Learn the Principle of Least Privilege and its importance in protecting servers.
- Identify potential security risks and attack surfaces associated with a virtual machine.
- Inspect the server's current network access configuration.
- Configure UFW to block incoming connections by default.
- Enable SSH access for remote server management.
- Permit TCP connections on port 8080 for the web application.
- Document the implementation process and present the results in a well-organized GitHub portfolio.

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
| `docker --version` | Checks the installed Docker version to confirm its availability. |
| `docker ps` | Lists the containers that are currently running. |
| `curl -i http://localhost:8080` | Tests whether the locally hosted web application can be accessed and displays its HTTP response. |
| `sudo ufw allow ssh` | Adds a firewall rule to permit SSH connections. |
| `sudo ufw default deny incoming` | Configures the firewall to block incoming connections by default. |
| `sudo ufw default allow outgoing` | Sets outgoing network connections to be allowed by default. |
| `sudo ufw enable` | Turns on the UFW firewall and applies its configured rules. |
| `sudo ufw status verbose` | Shows the firewall status, default policies, and active rules in detail. |
| `sudo ufw allow 8080/tcp` | Adds permission for incoming TCP traffic on port 8080. |
| `sudo ufw status numbered` | Displays firewall rules with their corresponding numbers for easier management. |

## Screenshots and Evidence

| Evidence File | Description |
|---|---|
| `vulnerable-app-running.png` | Shows the active Nginx container and evidence of a successful HTTP response. |
| `firewall-activated.png` | Captures the enabled UFW firewall and its configured default policies. |
| `firewall-port-allowed.png` | Presents the numbered firewall rules and the results of the web application connectivity test. |

All screenshots are stored in the `screenshots/` directory to keep the laboratory evidence organized and accessible for review.

## Skills Acquired

- Implementing basic Linux server security measures.
- Configuring and maintaining host-based firewall rules.
- Managing network access by controlling specific ports.
- Deploying and testing Docker-based web applications.
- Creating clear and structured technical reports using Markdown.
- Organizing laboratory documentation and supporting evidence in a GitHub repository.

## Mission Completion

This laboratory activity is considered complete when the UFW firewall has been properly configured, its status and rules have been verified, the technical documentation has been prepared, all three required screenshots have been uploaded, and the completed changes have been committed to the GitHub repository.

**Note:** All descriptions, command results, and screenshots must correspond to the actual commands executed and the output observed in the laboratory environment.
