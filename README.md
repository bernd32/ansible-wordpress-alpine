# WordPress Deployment with Ansible on Alpine Linux

Automated deployment of a two-tier WordPress application using Ansible on Alpine Linux servers.

## 🎯 Project Overview

This project demonstrates Infrastructure as Code (IaC) principles by automating the deployment of a production-ready WordPress environment with separated web and database tiers.

### Architecture
- **Web Server (192.168.88.50)**: Nginx + PHP-FPM serving WordPress
- **Database Server (192.168.88.60)**: MariaDB with network access restricted to web server only

Both servers run on KVM/QEMU VM based on Alpine Linux. 

## 🛠 Technology Stack

- **Configuration Management**: Ansible 2.15+
- **Operating System**: Alpine Linux 3.19+
- **Web Server**: Nginx
- **Application Server**: PHP-FPM 8.5
- **Database**: MariaDB 11.4
- **Application**: WordPress 6.4
- **Security**: Ansible Vault for secrets management

## 📋 Prerequisites

- Ansible 2.15 or higher
- SSH key-based authentication configured
- Two Alpine Linux hosts with Python 3 installed

## 🔧 Installation

### 1. Install Ansible Galaxy collections

```bash
ansible-galaxy collection install -r requirements.yml
```

### 2. Edit inventory/inventory.ini

### 3. Set up secrets

Create your own vault password and encrypt secrets:
```
ansible-vault edit inventory/group_vars/all/vault.yml
```

4. Deploy

```
ansible-playbook site.yml --ask-vault-pass
```


