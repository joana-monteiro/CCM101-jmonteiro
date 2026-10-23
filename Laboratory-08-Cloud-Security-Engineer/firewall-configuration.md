# Checkpoint 6 - Firewall Configuration Report

## Overview

This report documents the UFW firewall settings applied to protect the `secure-web-app` Nginx container during Laboratory Activity 8. The configuration uses a Default Deny policy for incoming connections while allowing SSH access for server administration and permitting TCP traffic on the designated port used by the web application.

## 1. Commands Executed

### Allow SSH Connections

```bash
sudo ufw allow ssh
```

**Purpose:** Allows SSH connections so administrators can access and manage the server remotely.

### Set the Default Firewall Policies

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

**Purpose:** Rejects incoming connections unless they are permitted by an explicit rule, while allowing outgoing network traffic by default.

### Activate the Firewall

```bash
sudo ufw enable
```

**Purpose:** Enables UFW and applies the configured firewall policies and rules.

### Check the Firewall Configuration

```bash
sudo ufw status verbose
```

**Purpose:** Shows whether the firewall is active, displays its default policies, and lists the configured rules with additional details.

### Permit Web Application Traffic

```bash
sudo ufw allow 8080/tcp
```

**Purpose:** Allows incoming TCP connections through port `8080`, which is designated for accessing the web application.

### View Numbered Firewall Rules

```bash
sudo ufw status numbered
```

**Purpose:** Displays the firewall rules in a numbered list, making it easier to review, identify, and manage individual entries.

### Verify Web Application Accessibility

```bash
curl -i http://localhost:8080
```

**Purpose:** Sends an HTTP request to the web application published on the local host and displays the response headers along with the returned content.

---

## 2. Importance of Allowing SSH Before Enabling UFW

Allowing SSH before activating UFW is an important precaution when managing a remote server. If the firewall is enabled while incoming SSH connections are blocked, an administrator could lose remote access and might need an alternative method to regain control of the machine.

Configuring the SSH rule beforehand helps preserve administrative connectivity while the remaining firewall settings are applied.

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

The UFW configuration strengthens server security by restricting incoming network connections and permitting only the services required for administration and web application access. Applying a Default Deny policy helps reduce unnecessary exposure to external connections.

To confirm that the configuration is working as intended, I should inspect the firewall status, review the numbered rules, and test the web application's accessibility. Actual terminal screenshots should be included as evidence that the firewall settings were applied and verified successfully.
