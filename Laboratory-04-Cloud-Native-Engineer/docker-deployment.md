# Checkpoint 5 — The Container Lifecycle

This document presents the fundamental Docker commands used to manage the lifecycle of a container. The process covers identifying running containers, stopping a container, verifying its status, and permanently removing it from the Docker environment.

<br>

## Container Lifecycle Commands

### 1. View Running Containers

**Command:**

```bash
docker ps
```

**Description:**

Displays information about all currently running containers, including the container ID, image, command, creation time, current status, port mappings, and container name. This command is useful for identifying which containers are currently active.

**Terminal Output:**

```text
CONTAINER ID   IMAGE   COMMAND                  STATUS         PORTS                  NAMES
xxxxxxxxxxxx   nginx   "/docker-entrypoint..."  Up             0.0.0.0:8080->80/tcp   server-nginx
```

The output indicates that the **`server-nginx`** container is currently running.

**Note:** To display all containers, including those that have already stopped, use:

```bash
docker ps -a
```

---

<br>

### 2. Stop the Running Container

**Command:**

```bash
docker stop server-nginx
```

**Description:**

Stops the specified container in a controlled manner. Docker sends a termination signal to the application, giving it an opportunity to shut down properly.

**Terminal Output:**

```text
server-nginx
```

The returned container name confirms that **`server-nginx`** was successfully stopped.

---

<br>

### 3. Verify the Container Status

**Command:**

```bash
docker ps -a
```

**Description:**

Displays all containers, including those that are no longer running. This allows the container's current status to be checked and confirms that `server-nginx` has stopped successfully.

**Terminal Output:**

```text
CONTAINER ID   IMAGE   COMMAND                  STATUS                     PORTS   NAMES
xxxxxxxxxxxx   nginx   "/docker-entrypoint..."  Exited (0) ...                    server-nginx
```

The **`Exited (0)`** status indicates that the container terminated successfully without an error.

**Note:** Using `docker ps` without the `-a` option only displays active containers, so a stopped container will not appear in the results.

---

<br>

### 4. Remove the Container

**Command:**

```bash
docker rm server-nginx
```

**Description:**

Removes the stopped `server-nginx` container from the Docker environment. This deletes the container's metadata and writable container layer.

**Terminal Output:**

```text
server-nginx
```

The output confirms that the container was successfully removed.

To verify that the container no longer exists, the following command was executed:

```bash
docker ps -a
```

**Terminal Output:**

```text
CONTAINER ID   IMAGE   COMMAND   CREATED   STATUS   PORTS   NAMES
```

The empty result confirms that **`server-nginx`** has been completely removed from the Docker environment.

---

<br>

## Summary

| # | Command                    | Purpose                               | Result                                              |
| - | -------------------------- | ------------------------------------- | --------------------------------------------------- |
| 1 | `docker ps`                | Displays currently running containers | `server-nginx` appears with an **Up** status        |
| 2 | `docker stop server-nginx` | Stops the running container           | Container successfully stopped                      |
| 3 | `docker ps -a`             | Checks the status of all containers   | Container displays **Exited (0)**                   |
| 4 | `docker rm server-nginx`   | Removes the stopped container         | Container deleted and no longer appears in the list |

Understanding and managing the Docker container lifecycle is an essential skill for a **Cloud-Native Engineer**. These commands provide a straightforward workflow for managing containers: **list → stop → verify → remove**.
