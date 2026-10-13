# Laboratory 5: The Cloud Data Engineer

<br>

## 🎯 Mission Overview
 
Congratulations! Your seamless deployment of containerized web servers has caught the attention of 
the senior architects. You have now been temporarily reassigned to the **Cloud Data Engineering Team** at 
CloudNova Technologies. 

In the cloud, data is everything. However, not all data is stored the same way. While traditional 
computers use hard drives (Block Storage) and shared network drives (File Storage), modern cloud applications 
rely heavily on **Object Storage** to store massive amounts of unstructured data like images, videos, and backups. 
The industry standard for this is Amazon S3, but today, you will deploy your very own S3-compatible cloud 
storage server using an open-source tool called **MinIO**. 

Using your KillerCoda Playground, you will combine your new Docker skills with your cloud storage knowledge to 
deploy a live object storage server, create a storage "bucket," and upload data over the web. 

> Remember: A cloud engineer doesn't just store data; they ensure it is scalable, accessible, and secure. 

---

## 📋 Objectives

By completing this laboratory activity, I was able to:

- Differentiate between Block, File, and Object Storage.
- Deploy an S3-compatible Object Storage server (MinIO) using Docker.
- Access a cloud service through a web interface using port forwarding.
- Create a storage bucket and upload objects (files) to the cloud.
- Document cloud storage operations using Markdown.
- Continue expanding a professional GitHub Cloud Computing Portfolio.

---

## Tools and Technologies

### 1. KillerCoda

KillerCoda is an online platform where I can practice Linux commands and cloud technologies. I used its Ubuntu Playground to run Docker commands and access the storage web console.

### 2. Docker

Docker allows applications to run inside containers. I used it to start the storage service, configure ports, and set the login credentials through environment variables.

### 3. MinIO

MinIO is an S3-compatible object storage service. In this activity, I used the alternative `pgsty/minio` community image because I could not download the official MinIO images in my KillerCoda environment.

I used the storage interface to create a private bucket named `client-photos` and upload sample files.

### 4. GitHub

GitHub helped me store and organize my laboratory files, while Markdown allowed me to write clear and organized documentation. I used both tools to document my progress and keep my Cloud Computing portfolio updated.

### 5. ChatGPT

I used ChatGPT to help me understand Docker commands, troubleshoot deployment problems, and improve my technical documentation. It also helped me understand unfamiliar concepts and find possible solutions when I encountered errors.

---

## Laboratory Procedure

In this activity, I followed several steps to set up and test the object storage service using Docker in KillerCoda.

1. **Download the Docker Image** – I tried downloading the official MinIO images. When the downloads failed, I used `pgsty/minio` as an alternative.
2. **Run the Container** – I used a Docker command to start the storage service and configure the required ports and login credentials.
3. **Check the Container** – I used `docker ps` to check whether the container was running.
4. **Access the Web Console** – I used the Traffic / Ports feature in KillerCoda and opened port `9001`.
5. **Create a Bucket** – I created a private bucket named `client-photos` to organize my sample files.
6. **Upload Files** – I uploaded `App Instructions.txt` and `Reflection.webp` to test the storage interface.
7. **Document the Activity** – I recorded the commands and procedures in Markdown for my GitHub portfolio.

---

## Project Summary

In this laboratory, I practiced using Docker to run an object storage service and manage files through a web interface. I learned how to configure container ports, set environment variables, check container status, create a bucket, and upload files.

Although I encountered problems downloading the official MinIO images, I continued the activity using an alternative image. This gave me an opportunity to practice troubleshooting and understand the importance of checking software compatibility.

The activity also reminded me to keep stored files private and protect administrator credentials. Overall, I gained practical experience with Docker and object storage that I can apply to future cloud computing projects.



