# Laboratory 08 — The Cloud Security Engineer

## Mission Overview

Laboratory Activity 08 focuses on securing an Ubuntu server using UFW (Uncomplicated Firewall). The activity involves running an Nginx web application through Docker, checking network connectivity, and configuring firewall rules to restrict unauthorized access while allowing essential services.

## Objectives

- Understand the Principle of Least Privilege.
- Inspect running containers and existing firewall settings.
- Apply a default-deny policy for incoming connections.
- Allow SSH for remote administration and TCP port 8080 for web access.
- Verify firewall rules and document the results in GitHub.

## Tools and Technologies

- Ubuntu Linux
- Docker and Nginx
- UFW Firewall
- cURL
- Markdown and GitHub

## Commands Executed

| Command                           | Purpose                                                     |
| --------------------------------- | ----------------------------------------------------------- |
| `docker --version`                | Verifies Docker installation.                               |
| `docker ps`                       | Checks running containers.                                  |
| `curl -i http://localhost:8080`   | Tests Nginx connectivity and HTTP response.                 |
| `sudo ufw allow ssh`              | Permits SSH connections for remote management.              |
| `sudo ufw default deny incoming`  | Blocks incoming connections unless explicitly allowed.      |
| `sudo ufw default allow outgoing` | Allows outgoing connections by default.                     |
| `sudo ufw enable`                 | Activates the firewall.                                     |
| `sudo ufw status verbose`         | Verifies firewall status and policies.                      |
| `sudo ufw allow 8080/tcp`         | Allows access to the web application through TCP port 8080. |
| `sudo ufw status numbered`        | Lists firewall rules for verification and management.       |

## Skills Acquired

This activity developed practical skills in Linux server security, firewall configuration, Docker container management, network access control, connectivity testing, and technical documentation using Markdown.

## Mission Completion

The mission is complete when the firewall is enabled, SSH and port 8080 access are configured, the rules and application connectivity are verified, and all required screenshots and documentation are committed to the GitHub repository.

**Security Note:** Configure and verify the SSH allow rule before enabling UFW on a remote server to avoid losing access. Only report results confirmed by actual command output and screenshots.
