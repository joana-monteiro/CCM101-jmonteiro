# Checkpoint 2: System Baseline Report

## 1. Memory (RAM) Usage

I used the `free -h` command to examine the server's memory usage. It displays the total RAM, the amount currently being used, and the available memory for running applications.

### Results

- **Total RAM:** 1.9 GiB
- **RAM in use:** 426 MiB
- **Available RAM:** 1.4 GiB

The results indicate that most of the server's memory is still available for other processes and applications.

---

## 2. Disk Storage Capacity

I executed the `df -h` command to inspect the server's disk usage. It shows the total filesystem capacity, used space, available storage, and percentage of disk space occupied.

### Results for the Root (`/`) Filesystem

- **Total storage:** 19 GiB
- **Used storage:** 5.5 GiB
- **Available storage:** 13 GiB
- **Storage utilization:** 30%

Approximately 30% of the root filesystem is occupied, leaving around 13 GiB of available storage for additional files and applications.

---

## 3. Running Processes and CPU Load

I used the `top` command to monitor active processes, CPU utilization, and the server's overall workload in real time.

### Observations

- **Total tasks:** 129
- **Running tasks:** 1
- **Sleeping tasks:** 128
- **CPU usage:** 0.0% user and 0.0% system
- **CPU idle:** 99.7%
- **Load average:** 0.00, 0.00, 0.00

The results show that the CPU was mostly idle during the observation. The low load average indicates that the server was experiencing minimal processing demand at that time.

---

## Why Checking Disk Space Matters Before a Traffic Surge

Monitoring disk capacity before a sudden increase in traffic helps reduce the risk of service interruptions. Server logs, temporary files, cached data, and container images can gradually consume available storage. When a disk reaches its capacity, applications may encounter errors while saving data, and some services may become slow or unavailable.

---

## Summary Table

| Resource | Total Capacity | Used | Available / Status |
|---|---|---|---|
| RAM | 1.9 GiB | 426 MiB | 1.4 GiB available |
| Root disk (`/`) | 19 GiB | 5.5 GiB | 13 GiB available; 30% used |
| CPU | — | 0.0% user / 0.0% system | 99.7% idle; load average 0.00 |

**Baseline Summary:** The server had 1.4 GiB of available RAM and approximately 13 GiB of free root storage. CPU activity was minimal during the inspection. These measurements establish a baseline for comparing resource utilization during future workloads and increased traffic.

