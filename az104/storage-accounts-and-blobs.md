---
id: storage-accounts-and-blobs.md
aliases: []
tags:
  - #azure
  - #az-104
  - #az104
  - #cloud
  - #cloud-components
  - #az104-course
  - #danlachance
  - #ghlearning
---

# Storage accounts and blobs

- Each storage account has its own pricing model

- Available accounts:
  - General-purpose v1 (legacy)
  - General-purpose v2
  - BlobStorage (legacy)
  - BlockBlobStorage
  - FileStorage

- Differences between various storage accounts:
  - Supported Services:  Blob, File, Queue, Table, Disk, and Data Lake Gen2
  - Performance Tiers: Standard and Premium
  - Access Tiers: 
    - Hot
    - Cool
    - Cold
    - Archive
    - Smart

  - Replication
  - Deployment Model

## Storage Account Settings

- Access keys
- Shared access signatures -> Provides time-limited access to a subset of things
- Encryption
- Geo-replication

## Storage Account Blobs 

- Blob public access 
- Versioning and snapshots
- Blob lifecycle management
- Soft delete

- Types:
  - Block 
  - Append 
  - Page

## Storage Account Practical

- Each storage account is deployed in a region, so depending on regions, multiple storage accounts may be needed

## Blob Upload

- Methods of uploading and managing blobs:
  - Portal 
  - PowerShell 
  - Bash 
  - Storage Explorer
  - AzCopy

- Blob Soft Delete -> Recycle bin functionality for blobs, enabled by default, with retention period of 7 days

- Blob Soft Delete is also applicable for Blob versions and Blob snapshots

- Blob containers and previous versions of blobs can be made immutable, for a **Legal Hold**, **Time-based retention** (the latter cannot be randomly undone)

- Archived data cannot immediately be accessed, it has to be rehydrated first

### Powershell (CloudShell or Local)

- Select subscription
- Upload files to use

```powershell

cls 
dir

get-command *storageaccount*

get-azstorageaccount

```

### Bash

```bash
az storage account list --query [].name
```

Output:
[
  "trialstorageaccount1234"
]

### Storage Explorer 

- Completely free, installable, GUI for managing storage accounts and resources 

> [!IMPORTANT]
> Allows creation of folders within blobs which is not allowed in the portal or cli

### AzCopy

- Logging in with AzCopy does not work for an external account 

- Requires Storage Blob Data Owner permissions

- In my case, it still wasnt enough, I had to use a SAS key with the container to copy files to Azure 

```bash
azcopy cp "<filename>" "https://trialstorageaccount1234.blob.core.windows.net/<container-name>?<sas-key>"
```

