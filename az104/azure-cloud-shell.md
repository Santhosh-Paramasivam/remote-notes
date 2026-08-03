---
id: azure-cloud-shell.md
aliases: []
tags:
  - #azure
  - #az-104
  - #az104
  - #cloud
  - #cloud-components
---

# Azure Cloud Shell

- A bash and powershell terminal available for use within the azure portal, from the browser

- You need an Azure Subscription to use Azure CloudShell

- Features:
  - Terminal as a service
  - Automatically updated and patched
  - Always "logged in" and with the appropriate permissions
  - **Provides storage for** SSH keys, scripts and more
  - **Cloud Shell editor** can be used to edit files

## Working

- Cloud shell sessions are terminated after 20 minutes of inactivity

- A new or older disk image or file share is mounted as a **Cloud Drive**, and contains files to persist across Cloud Shell sessions [persisting-cloud-shell](https://learn.microsoft.com/en-us/azure/cloud-shell/persisting-shell-storage)

- To open a file, click the `{}` symbol or in Classic mode, type `code filename.txt` in Bash

- Cloud shell has many builtin tools including:
  - tmux
  - AZCopy, Azure Functions CLI
  - Git
  - Maven
  - Docker, Kubectl
  - MySQL, PostgreSQL

## When not to use

- Keep the same cloud shell window open for more than 20 minutes for have long running tasks

- Need sudo permissions
  
- If you want to install tools not in Cloud Shell

- Storage across regions, since you're forced to store files only in a selected geographic region

