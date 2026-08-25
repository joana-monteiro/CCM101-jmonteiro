# Infrastructure Report

## 1. System Overview

This report presents the configuration, hardware resources, network settings, storage capacity, and filesystem structure of the Ubuntu cloud server. The system information was obtained using standard Linux utilities, including `cat`, `uname`, `lscpu`, `free`, `hostname`, `ip`, `df`, and `findmnt`.

---

## 2. Operating System

The cloud server is running **Ubuntu 24.04.4 LTS (Noble Numbat)** with the Linux 6.8 kernel.

| Property         | Details            |
| ---------------- | ------------------ |
| Operating System | Ubuntu 24.04.4 LTS |
| Version ID       | 24.04              |
| Codename         | Noble Numbat       |
| Kernel           | 6.8.0-138-generic  |
| System Type      | Linux              |

### Command Used

```bash
cat /etc/os-release
uname -r
```

### Result

```text
Ubuntu 24.04.4 LTS
Kernel: 6.8.0-138-generic
Codename: noble
```

---

## 3. CPU / Processor

The server uses a virtualized **Intel Xeon E312xx processor based on the Sandy Bridge architecture**. One virtual CPU is assigned to the cloud environment.

| Property                       | Details                    |
| ------------------------------ | -------------------------- |
| Processor                      | Intel Xeon E312xx          |
| Architecture Generation        | Sandy Bridge               |
| CPU Cores/Processors Available | 1                          |
| Reported CPU Frequency         | 2.0 GHz                    |
| Virtual BIOS Model             | RHEL-9.6.0 PC (Q35 + ICH9) |

### Command Used

```bash
lscpu | grep "Model name"
lscpu | grep "^CPU(s):"
```

### Result

```text
Model name: Intel Xeon E312xx (Sandy Bridge, IBRS update)
CPU(s): 1
```

### Observation

The cloud server is configured with **one virtual CPU**, which is appropriate for lightweight workloads such as Linux administration, development, testing, scripting, and basic server applications.

---

## 4. Memory / RAM

The server has approximately **1.9 GiB of physical memory** and **1 GiB of swap space**.

| Resource      |  Amount |
| ------------- | ------: |
| Total RAM     | 1.9 GiB |
| Used RAM      | 608 MiB |
| Free RAM      | 645 MiB |
| Buffer/Cache  | 818 MiB |
| Available RAM | 1.3 GiB |
| Total Swap    | 1.0 GiB |
| Swap Used     |     0 B |

### Command Used

```bash
free -h
```

### Observation

Approximately **1.3 GiB of memory remains available**, while the configured swap space is currently unused. This indicates that the server was operating without significant memory pressure when the system information was collected.

---

## 5. Hostname and Network Configuration

The hostname assigned to the server is:

```text
ubuntu
```

### Command Used

```bash
hostname
hostname -I
```

### Network Addresses

| Interface / Address | Details      |
| ------------------- | ------------ |
| Hostname            | `ubuntu`     |
| Primary Network IP  | `172.30.1.2` |
| Docker Network IP   | `172.17.0.1` |
| Loopback Address    | `127.0.0.1`  |

The hostname identifies the server within its environment, while the listed network addresses correspond to the primary network, Docker bridge, and local loopback interfaces.

---

## 6. Network Interfaces

The server contains three visible network interfaces: `lo`, `enp1s0`, and `docker0`.

### 6.1 Loopback Interface — `lo`

```text
127.0.0.1/8
::1/128
```

The loopback interface provides communication between applications and services running on the same server. It does not require an external network connection.

### 6.2 Primary Network Interface — `enp1s0`

```text
IPv4: 172.30.1.2/24
Broadcast: 172.30.1.255
MTU: 1450
State: UP
```

The `enp1s0` interface serves as the primary network connection for the Ubuntu server. Its `UP` state indicates that the interface is active.

### 6.3 Docker Bridge — `docker0`

```text
IPv4: 172.17.0.1/16
State: DOWN
```

The `docker0` interface is associated with Docker's default bridge networking and is used to provide network connectivity to Docker containers when the Docker networking service is active.

### Command Used

```bash
ip addr
```

---

## 7. Disk Storage

The server uses an **ext4 filesystem** for its primary root partition.

| Filesystem   |   Size |   Used | Available | Usage |
| ------------ | -----: | -----: | --------: | ----: |
| `/dev/vda1`  |  19 GB | 5.4 GB |     13 GB |   30% |
| `/dev/vda16` | 881 MB | 117 MB |    703 MB |   15% |
| `/dev/vda15` | 105 MB | 6.2 MB |     99 MB |    6% |

### Root Filesystem

```text
/dev/vda1
Size: 19G
Used: 5.4G
Available: 13G
Usage: 30%
Mounted: /
Filesystem: ext4
```

### Command Used

```bash
df -h
```

### Observation

The primary root partition has approximately **13 GB of available storage**, with only **30% of its capacity currently utilized**. This provides sufficient space for additional software, configuration files, system logs, development resources, and laboratory projects.

---

## 8. Mount Points and Filesystems

The Ubuntu system contains several filesystem types used for different system functions.

| Mount Point      | Source       | Filesystem |
| ---------------- | ------------ | ---------- |
| `/`              | `/dev/vda1`  | ext4       |
| `/boot`          | `/dev/vda16` | ext4       |
| `/boot/efi`      | `/dev/vda15` | vfat       |
| `/dev`           | `udev`       | devtmpfs   |
| `/dev/shm`       | `tmpfs`      | tmpfs      |
| `/run`           | `tmpfs`      | tmpfs      |
| `/proc`          | `proc`       | proc       |
| `/sys`           | `sysfs`      | sysfs      |
| `/sys/fs/cgroup` | `cgroup2`    | cgroup2    |

### Command Used

```bash
findmnt
```

These mount points support essential operating system functions, including device management, temporary runtime data, process information, system configuration, and boot-related files.

---

## 9. Root Filesystem Configuration

The primary root filesystem is mounted using the following configuration:

```text
/dev/vda1 on /
Filesystem: ext4
Mount options:
rw,relatime,discard,errors=remount-ro,commit=30
```

### Important Mount Options

| Option              | Purpose                                                                  |
| ------------------- | ------------------------------------------------------------------------ |
| `rw`                | Allows the filesystem to be read from and written to.                    |
| `relatime`          | Updates file access times in a more efficient manner.                    |
| `discard`           | Enables storage discard operations such as TRIM when supported.          |
| `errors=remount-ro` | Remounts the filesystem as read-only if serious filesystem errors occur. |
| `commit=30`         | Controls the interval for committing filesystem journal data.            |

---

## 10. Docker Infrastructure

A Docker bridge interface is present on the server:

```text
docker0
172.17.0.1/16
```

The interface is currently reported as:

```text
state DOWN
NO-CARRIER
```

This indicates that the Docker bridge configuration exists, but there is currently no active network connection through the bridge. The interface can be used for container networking when Docker services and containers are actively running.

---

## 11. Infrastructure Summary

| Component        | Configuration              | Status    |
| ---------------- | -------------------------- | --------- |
| Cloud Server     | Ubuntu virtual machine     | Running   |
| Operating System | Ubuntu 24.04.4 LTS         | Active    |
| Kernel           | 6.8.0-138-generic          | Active    |
| CPU              | 1 × Intel Xeon virtual CPU | Available |
| RAM              | 1.9 GiB                    | Available |
| Swap             | 1.0 GiB                    | Available |
| Root Storage     | 19 GB                      | 30% Used  |
| Primary Network  | `enp1s0`                   | UP        |
| Docker Bridge    | `172.17.0.1/16`            | Inactive  |
| Root Filesystem  | ext4                       | Mounted   |
| Boot Filesystem  | ext4                       | Mounted   |
| EFI Partition    | vfat                       | Mounted   |

---

## 12. Overall Infrastructure Assessment

The Ubuntu cloud server is configured as a lightweight virtualized Linux environment with **one virtual CPU, approximately 1.9 GiB of RAM, 1 GiB of swap space, and a 19 GB primary storage volume**.

The available resources are adequate for fundamental cloud computing laboratory activities, Linux system administration, software development, scripting, file management, and lightweight server applications.

### Resource Utilization

* **Memory:** Approximately 608 MiB currently used
* **Available Memory:** Approximately 1.3 GiB
* **Root Storage:** 5.4 GB currently used
* **Available Storage:** Approximately 13 GB
* **Swap:** 0 B currently used
* **Primary Network:** Active through `enp1s0`
* **Docker Bridge:** Configured but currently inactive
* **Root Filesystem:** ext4 and mounted with read/write access

---

## 13. Conclusion

The infrastructure assessment confirms that the cloud server is operating on **Ubuntu 24.04.4 LTS** with the Linux 6.8 kernel and a virtualized Intel Xeon processor. The environment provides sufficient CPU, memory, storage, and networking resources for basic cloud computing and Linux administration activities.

The primary storage partition is currently **30% utilized**, leaving approximately **13 GB of available capacity**. Memory consumption is moderate, and the configured swap space remains unused. The `enp1s0` interface is active and provides the server's primary network connectivity, while the Docker bridge is available for container-based networking when required.

Overall, the server provides a suitable and functional environment for **cloud infrastructure training, Linux system administration, scripting, software development, server configuration, and laboratory exercises**.
