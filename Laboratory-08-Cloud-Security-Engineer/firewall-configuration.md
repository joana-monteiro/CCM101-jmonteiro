# Checkpoint 6 – Firewall Configuration Report

## Overview

This report presents the UFW firewall configuration implemented to secure the `secure-web-app` Nginx container during Laboratory Activity 8. The setup follows a **Default Deny** approach for incoming connections while allowing SSH for remote server administration and permitting TCP traffic on port `8080` for web application access.

## 1. Commands Executed

### Allow SSH Connections

```bash
sudo ufw allow ssh
```

**Purpose:** Permits SSH connections, enabling administrators to remotely access and manage the server.

### Configure the Default Firewall Policies

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

**Purpose:** Blocks incoming connections unless explicitly permitted by a firewall rule while allowing outgoing network traffic by default.

### Enable the Firewall

```bash
sudo ufw enable
```

**Purpose:** Activates UFW and applies the configured default policies and firewall rules.

### Verify the Firewall Status

```bash
sudo ufw status verbose
```

**Purpose:** Displays the firewall's current status, default security policies, configured rules, and additional configuration details.

### Allow Web Application Traffic

```bash
sudo ufw allow 8080/tcp
```

**Purpose:** Permits incoming TCP traffic on port `8080`, allowing connections to the web application through its designated port.

### Display Numbered Firewall Rules

```bash
sudo ufw status numbered
```

**Purpose:** Lists the configured firewall rules with assigned numbers, making it easier to inspect, identify, and manage individual rules.

### Test Web Application Accessibility

```bash
curl -i http://localhost:8080
```

**Purpose:** Sends an HTTP request to the web application through the local host and displays the response headers and content to help verify its availability.

---

## 2. Importance of Allowing SSH Before Enabling UFW

Configuring the SSH rule before activating UFW is an essential precaution when administering a remote server. Enabling the firewall without first permitting SSH could block remote administrative connections and potentially lock the administrator out of the system.

By establishing the SSH permission in advance, administrators can maintain remote access while applying the remaining firewall configurations.

---

## 3. Final Firewall Policy

| Configuration | Expected Result |
|---|---|
| Firewall Status | Active |
| Default Incoming Policy | Deny |
| Default Outgoing Policy | Allow |
| SSH Access | Allowed |
| TCP Port 8080 | Allowed |

---

## 4. Security Summary

The UFW configuration improves server security by controlling incoming network traffic and allowing only the connections required for remote administration and web application access. The Default Deny policy minimizes unnecessary network exposure by blocking incoming connections that do not match an explicitly permitted rule.

To validate the configuration, the firewall status and numbered rules should be inspected, and the web application's accessibility should be tested. Actual terminal screenshots should also be provided as supporting evidence to demonstrate that the firewall rules were configured and verified successfully.
