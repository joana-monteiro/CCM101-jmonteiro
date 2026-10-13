# Checkpoint 5 — Technical Documentation

This document explains how I deployed an S3-compatible object storage service using Docker in the KillerCoda Ubuntu Playground. It includes starting the container, opening the web console, creating a bucket, uploading files, and setting environment variables.

---

## A. Docker Deployment

I tried downloading the official `minio/minio` and `quay.io/minio/minio` images, but both attempts failed in my KillerCoda environment. To continue the activity, I used `pgsty/minio` as an alternative image.

**Note:** `pgsty/minio` is not the official MinIO image. Its features and configuration may differ from the original MinIO service, so compatibility with the laboratory instructions should be checked.

### Commands Used

**1. Download the Docker image**

```bash
docker pull pgsty/minio
```

**2. Create and run the container**

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
-e "MINIO_ROOT_USER=cloudadmin" \
-e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
pgsty/minio server /data --console-address ":9001"
```

**3. Check the container status**

```bash
docker ps
```

This command allowed me to check if the container was running and if ports `9000` and `9001` were properly mapped.

---

## B. Accessing the Web Console

I used the Traffic / Ports feature in KillerCoda to open the storage console. I entered port `9001` and clicked **Access** to open it in my browser.

| Item | Details |
|---|---|
| Web Console Port | `9001` |
| Storage API Port | `9000` |
| Access Procedure | Traffic / Ports → Enter `9001` → Access |

After opening the console, I entered the administrator username and password configured in the Docker command. This allowed me to access the available storage management features.

---

## C. Creating a Bucket and Uploading Files

I created a bucket named `client-photos` to store sample files for a photo-sharing application. I set the bucket to private and uploaded two files.

| Item | Details |
|---|---|
| Bucket Name | `client-photos` |
| Access Setting | Private |
| First File | `App Instructions.txt` |
| Second File | `Reflection.webp` |

This activity helped me understand how buckets organize files in object storage and how to upload objects through a web console. Keeping the bucket private also demonstrated the importance of protecting stored files from unauthorized access.

---

## D. Environment Variable Configuration

I used environment variables to set the administrator login credentials when starting the container.

| Environment Variable | Value | Purpose |
|---|---|---|
| `MINIO_ROOT_USER` | `cloudadmin` | Sets the administrator username. |
| `MINIO_ROOT_PASSWORD` | `CloudNova2026!` | Sets the administrator password. |

The `-e` option allows environment variables to be passed into the container. These variables were intended to configure the credentials used to access the storage console.

### Security Considerations

For actual projects, passwords should be stored securely instead of being written directly in Docker commands. Command-line arguments and environment variables may expose sensitive information through shell history or container settings. Using a secure secrets-management solution is a safer approach.

---

## Conclusion

This laboratory activity helped me understand how to use Docker to deploy and manage an object storage service. I learned how to download an image, run a container, map ports, configure environment variables, access a web console, create a bucket, and upload files.

I also learned that alternative Docker images may differ from official images and that compatibility should be checked before using them. Overall, this activity gave me practical experience with container deployment and the basic operations of object storage.
