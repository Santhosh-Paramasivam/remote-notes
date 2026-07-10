---
id: azure-storage-services
aliases: []
tags:
  - #azure
  - #cloud
  - #cloud-components
---

- [Azure Storage Services](#azure-storage-services)
  - [Commonly used services](#commonly-used-services)
    - [Azure Blob Storage](#azure-blob-storage)
    - [Azure Disk Storage](#azure-disk-storage)
    - [Azure File Storage](#azure-file-storage)
    - [\* Azure Queue Storage](#-azure-queue-storage)
    - [\* Azure Table Storage](#-azure-table-storage)
    - [Azure Data Box / Azure Databox Heavy](#azure-data-box--azure-databox-heavy)
    - [Azure Archive Storage](#azure-archive-storage)
    - [Azure Data Lake Storage](#azure-data-lake-storage)
  - [Storage Comparison](#storage-comparison)
    - [Storage Accounts](#storage-accounts)
  - [Core Storage Services](#core-storage-services)
  - [Performance Tiers](#performance-tiers)
    - [Premium](#premium)
    - [Standard](#standard)
  - [Access Tiers (Blob Storage)](#access-tiers-blob-storage)
    - [Hot](#hot)
    - [Cool](#cool)
    - [Archive](#archive)
    - [Tiering](#tiering)
  - [Replication and Data Redundancy](#replication-and-data-redundancy)
    - [Primary Region Redundancy](#primary-region-redundancy)
      - [Locally Redundant Storage (LRS)](#locally-redundant-storage-lrs)
      - [Zone-redundant storage (ZRS)](#zone-redundant-storage-zrs)
    - [Secondary Region Redundancy](#secondary-region-redundancy)
      - [Geo-redundant storage (GRS)](#geo-redundant-storage-grs)
      - [Geo-zone-redundant storage (GZRS)](#geo-zone-redundant-storage-gzrs)
    - [Redundancy with Read Access](#redundancy-with-read-access)
  - [Azure Blob](#azure-blob)
    - [Object Storage Principles](#object-storage-principles)
    - [Blob Hierarchy](#blob-hierarchy)
    - [Blob Types](#blob-types)

# Azure Storage Services

## Commonly used services

### Azure Blob Storage

- *Object Serverless Storage*

- Store very large files and large amounts of unstructured files

- Pay for what you store, unlimited storage, no-resizing volumes, filesystem protocols

### Azure Disk Storage

- A virtual volume.

- SSD or HDD, encryption by default, attach volume to VMs

### Azure File Storage

- A shared volume that you can *access and manage like a file server*

- Used where a shared resource might be needed or if those protocols are useful for services or applications

> [!NOTE]
> The services with an * before them are **not** storage services, but have storage in the name prompting me to put them in this list

### * Azure Queue Storage

- *Messaging queue*

- A data store for queuing and reliably delivering messages between applications

### * Azure Table Storage 

- *Wide-Column NoSQL Database* 

- NoSQL store that hosts unstructured data independent of any schema

### Azure Data Box / Azure Databox Heavy

- To move terabytes or petabytes of data, networking might be too slow

- In such a case, Microsoft sends a dude with a *briefcase computer and storage* designed with all the data

### Azure Archive Storage

- *Long term cold storage* for when you need to hold onto files for years on the cheapest storage option

### Azure Data Lake Storage

- A centralized repository that allows you to store all your structured and unstructured data at any scale

## Storage Comparison

### Storage Accounts

![storage-accounts-comparison](images/2026-07-06-230319_hyprshot.png) 

- [azure-storage-account-overview](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-overview)

- Provides a unique namespace for storage objects

## Core Storage Services

- **Azure Blob**: Also includes support for big data analytics through Data Lake Storage Gen2

- **Azure Files**: Managed file shares

- **Azure Queues**

- **Azure Tables**

- **Azure Disks**: Block-level storage volumes for Azure VMs

## Performance Tiers

### Premium

- Higher IOPS (Input / Output Operations Per Second)  

- Stored on SSDs

- Optimized for low latency

- Higher throughput

> [!NOTE]
> In an SSD
> No moving parts and data is distributed randomly

- Use cases:
  - Interactive workloads
  - Analytics
  - AI or ML
  - Data Transformation

### Standard 

- Stored on HDDs

- Varied performance based on access tier (Hot, Cold, Archive)

- Use cases:
    - Backup and disaster recovery
    - Media content
    - Bulk data processing

> [!NOTE]
> In an HDD
> Very good at writing or reading large amounts of data that is close together

## Access Tiers (Blob Storage)

### Hot  

- Data that's accessed frequently
 
- Highest storage cost, lowest access cost

### Cool 

- Data that's infrequently accessed and stored for at least 30 days

- Lower storage cost, higher access cost

- Must be stored for at least 30 days to avoid *early deletion penalties*

- Use cases:
  - Short-term backup and disaster recovery datasets
  - Older media content not frequently accessed but still expected to be immediately available
  - Large datasets that need to be stored cost effectively while more data is being gathered for future processing

### Archive

- Data that's rarely accessed and stored for at least 180 days

- Must be stored for at least 180 days to avoid *early deletion penalties*

- Lowest storage cost, highest access cost 

- Use cases:
  - Long-term backup, secondary backup, and archival datasets
  - Original raw data that must be preserved, even after it has been processed into final usable from
  - Compliance and archival that is stored but rarely ever accessed

### Tiering

- Account-level tiering: If an access isn't explicitly associated with a blob, then the access tier of the Storage Account is utilized

- Blob-level Tiering: You can set the tier of any blob. 

- Changing tiers happens instantly with the *exception of moving out of archive* which can take hours, and is called **Rehydration**

- Blob lifecycle Management: Rule-based policies to transition data to other tiers

## Replication and Data Redundancy

- When a Storage Account is created, you need to choose a replication type

- Replication stores data from:
  - Transient hardware failures
  - Planned events 
  - Network or power outages 
  - Massive natural disasters

### Primary Region Redundancy 

- Data is replicated 3 times in the primary region

- Used for disaster recovery and failover

####  Locally Redundant Storage (LRS) 

- *Copies data synchronously* within data centers

- Redundancy within availability zones

- Durability of 99.999999999 (11 nines durability)

- Cheapest possible redundancy

#### Zone-redundant storage (ZRS)

- *Copies data synchronously* across 3 availability zones

- Durability of 99.9999999999 (12 nines durability)

- Redundancy across availability zones

### Secondary Region Redundancy

- Replicate to a secondary region in case of primary regional disaster 

- The *secondary region is determined* based on the primary's pair region. You cannot manually select a different region.

- Secondary region isn't available for read or write access (except in event of failover)

- Used for disaster recovery and failover

#### Geo-redundant storage (GRS)

- Copies data *synchronously* in primary region (LRS)

- Copies data *asynchronously* to another region

- 99.99999999999999% (16 9's) of durability

####  Geo-zone-redundant storage (GZRS)

- Copies data *synchronously* in across 3 AZs in primary region (ZRS)

- Copies data *asynchronously* to another region (not necessarily LRS or ZRS there)

- 99.99999999999999% (16 9's) of durability

### Redundancy with Read Access 

- Exact same as GRS and GZRS except the *secondary region is fully synced with the primary*, as in, the data transfer is *synchronous between regions too*

- Read-access geo-redundant storage (RA-GRS)

- Read-access geo-zone-redundant storage (RA-GZRS)

- Used for **Read Replicas**

## Azure Blob

- Blob storage is a **object-store**

- [aws-object-storage](https://aws.amazon.com/what-is/object-storage/)

### Object Storage Principles

- *No folders* to avoid nesting/pathing inefficiency

- *Flat namespace*, "folders" are just metadata in the object 

- A blob or object consists of the actual data, metadata (usually key-value pairs), name (globally unique)

- Files are stored in *different data formats in the same place*, a particular object can have any type

- *All files have random access*, so incredibly fast and same performance even if the system is scaled up, allowing virtually unlimited scalability

- Used for *unstructured data such as images, videos and files, and for archival purposes* (even for data that isn't actively stored on Blob Storage)

- Globally unique identifier to identify each object uniquely

### Blob Hierarchy

- **Storage Account**
  - **Container1**
    - Blob1 -> Actual data being stored
    - Blob2
  - Container2
    - Blob3
    - Blob4

### Blob Types

- **Block blobs**:
  - Store text and binary data
  - Made up of blocks of data that are managed individually, at once, either uploaded or downloaded but not repeatedly appended to or modified
  - Store up to about 4.75 TB of data

- **Append blobs**:
  - Optimized (only) for append operations 
  - Ideal for scenarios such as logging data from virtual machine 

- **Page Blobs**:
  - Store random access files up to 8 TB in size 
  - Store virtual hard drive files, and serve as disks for Azure VMs
