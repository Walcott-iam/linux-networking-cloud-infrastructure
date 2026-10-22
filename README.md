# linux-networking-cloud-infrastructure# Linux, Networking & Cloud Infrastructure - Task 2

## Project Overview
This project demonstrates the deployment and configuration of a Linux server on Microsoft Azure. It covers securing SSH access, configuring Network Security Groups (NSG), Linux CLI operations (users, groups, permissions, processes), and deploying a live Nginx web service.

## 1. Cloud Deployment & Networking
- **Provider:** Microsoft Azure
- **VM Size:** Standard_B2ats_v2 (Free Tier)
- **OS:** Ubuntu Server 24.04 LTS
- **Security:** Generated a local RSA SSH key pair and used the public key for passwordless authentication.

### Network Security Group (NSG) Rules
Configured the Azure firewall to allow:
- Port 22 (SSH) for secure remote management.
- Port 80 (HTTP) to serve web traffic to the internet.

*[INSERT SCREENSHOT 1 HERE - Azure NSG Inbound Port Rules]*

## 2. Linux CLI & User Management
Connected to the VM via SSH and performed the following operations:

### SSH Connection
*[INSERT SCREENSHOT 2 HERE - Terminal showing successful SSH login]*

### Users and Groups
Created a dedicated group and user for cloud administration.
```bash
sudo groupadd cloudadmins
sudo useradd -m -g cloudadmins -s /bin/bash devops_user
sudo passwd devops_user
