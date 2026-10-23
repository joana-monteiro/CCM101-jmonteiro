# Checkpoint 2 - Security Audit Report

## Mission Information

- **Course:** CCM101 – Cloud Computing
- **Laboratory:** Activity 8
- **Mission:** The Cloud Security Engineer
- **Environment:** KillerCoda Ubuntu Playground
- **Application:** Nginx Web Server
- **Security Tool:** UFW (Uncomplicated Firewall)

---

## 1. Security Objectives

- Recognize the importance of regulating network access to cloud servers.
- Understand the Principle of Least Privilege (PoLP) and its role in protecting system resources.
- Identify the potential attack surface of a virtual machine.
- Configure a Default Deny firewall policy to restrict unauthorized connections.
- Permit only the network services necessary for the application to function.

---

## 2. Security Concepts

### Principle of Least Privilege (PoLP)

The Principle of Least Privilege involves granting users and services only the permissions required to complete their specific responsibilities. In cloud computing, applying this principle helps minimize unauthorized access, prevent unintended system modifications, and reduce the risks associated with excessive administrative privileges.

### Attack Surface

An attack surface consists of the possible entry points that malicious actors could exploit to access or compromise a system. For a virtual machine, these entry points may include exposed network ports, active services, vulnerable applications, and user accounts with unnecessary permissions.

### Default Deny Policy

A Default Deny policy rejects incoming network connections unless they are explicitly permitted by a firewall rule. This approach strengthens security by blocking unapproved traffic instead of relying solely on rules designed to identify and block specific threats.

---

## 3. Security Audit Plan

The audit involves preparing an Nginx web application running inside a Docker container and making it accessible through port `8080`. After preparing the application, I will configure UFW to reject incoming connections by default, allow SSH traffic for remote administration, and permit TCP connections on port `8080` for web application access.

This configuration aims to limit unnecessary network exposure while maintaining access to the services required for system administration and website operation.

---

## 4. Expected Firewall Rules

| Service | Port | Protocol | Action |
|---|---:|---|---|
| SSH Administration | 22 | TCP | Allow |
| Web Application | 8080 | TCP | Allow |
| All Other Incoming Traffic | Other ports | Any | Deny by default |

---

## 5. Audit Conclusion

Implementing restrictive firewall rules helps minimize unnecessary network exposure and reinforces the Principle of Least Privilege. By allowing only the required services and blocking other incoming connections by default, the server can maintain a more controlled network security configuration.

The final firewall settings and connectivity test results should be examined alongside the terminal screenshots captured during the laboratory activity to verify that the intended security rules were applied correctly.
