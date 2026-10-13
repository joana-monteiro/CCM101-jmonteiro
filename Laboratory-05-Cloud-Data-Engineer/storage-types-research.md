# Checkpoint 2 – Research: Types of Cloud Storage

## Comparison Table

Cloud storage has three main types: Block Storage, File Storage, and Object Storage. Each type organizes and manages data differently depending on its purpose and access requirements.

| Storage Type | How It Stores Data | Best Use | Cloud Provider Examples |
|---|---|---|---|
| **Block Storage** | Divides data into fixed-size blocks that work similarly to the storage sectors of a hard drive. | Databases, operating systems, and virtual machine storage that require fast data access. | Amazon EBS, Azure Managed Disks, Google Persistent Disk |
| **File Storage** | Organizes data into files and folders, making it easy to store, locate, and share information. | Shared documents, team folders, and applications that require multiple users to access the same files. | Amazon EFS, Azure Files, Google Filestore |
| **Object Storage** | Stores data as individual objects containing the file, metadata, and a unique identifier. | Images, videos, backups, and large collections of unstructured data. | Amazon S3, Azure Blob Storage, Google Cloud Storage |

## Understanding the Differences

- **Block Storage:** Works like a traditional hard drive by dividing information into blocks. It is useful for applications that require fast and frequent data access, such as databases and virtual machines.

- **File Storage:** Works like the folders on a computer. It allows users to organize files into directories and makes sharing information between multiple users or computers easier.

- **Object Storage:** Works like a large online storage repository. Each file is stored as a separate object with its own identifier and metadata, making it suitable for managing large amounts of images, videos, and backup files.

## Why Object Storage Is the Best Choice for User-Uploaded Images

Object Storage is an excellent choice for photo-sharing applications because it can store large numbers of images and expand as the application grows. It also allows images to be accessed through URLs or delivered using a Content Delivery Network (CDN), which can improve loading speed for users in different locations.

Instead of saving the actual image files directly in a database, the application can store the images in object storage and keep their URLs and related information in the database. This approach helps reduce database storage requirements and makes image management more efficient as the application grows.
