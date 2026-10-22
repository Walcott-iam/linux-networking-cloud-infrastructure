# Linux, Networking & Cloud Infrastructure 

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

![Inbound rule](https://github.com/Walcott-iam/linux-networking-cloud-infrastructure/blob/main/inbound%20rule.png)

## 2. Linux CLI & User Management
Connected to the VM via SSH and performed the following operations:

### SSH Connection
![Successful connection](https://github.com/Walcott-iam/linux-networking-cloud-infrastructure/blob/main/succesful%20login%20through%20terminal.png)

File Permissions
Demonstrated file permission changes using chmod. Restricted a file so only the owner can read and write.

bash
echo "Secret Cloud Data" > secret.txt
ls -l secret.txt
chmod 600 secret.txt
ls -l secret.txt
![File permission](https://github.com/Walcott-iam/linux-networking-cloud-infrastructure/blob/main/file%20permission.png)

## 3. Service Deployment & Process Management
Installed and managed the Nginx web server.

![Active running Ngnix](https://github.com/Walcott-iam/linux-networking-cloud-infrastructure/blob/main/active%20running%20ngnix.png)

```bash
sudo apt update
sudo apt install nginx -y
sudo systemctl status nginx
```

## 4. Users and Groups
Created a dedicated group and user for cloud administration.
```bash
sudo groupadd cloudadmins
sudo useradd -m -g cloudadmins -s /bin/bash devops_user
sudo passwd devops_user
```
![user.png](https://github.com/Walcott-iam/linux-networking-cloud-infrastructure/blob/main/-t-c%20user.png)

## 5. Test Connectivity
Successfully tested HTTP connectivity by accessing the VM's public IP in a web browser. The Nginx default welcome page loaded, proving the NSG firewall and web server were correctly configured.

![Welcome to Nginx](https://github.com/Walcott-iam/linux-networking-cloud-infrastructure/blob/main/welcome%20to%20ngnix.png)
