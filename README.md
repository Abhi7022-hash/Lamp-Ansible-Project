# 🚀 LAMP Stack Provisioning on AWS EC2 using Ansible

This project automates the provisioning of a **LAMP stack (Linux, Apache, MySQL, PHP)** on an **AWS EC2 Ubuntu instance** using **Ansible**. It demonstrates the use of Ansible Playbooks and Roles for configuration management and infrastructure automation.

---

## 📌 What is LAMP?

LAMP is a popular web server stack consisting of:

- **L**inux: Ubuntu (OS)
- **A**pache: Web server
- **M**ySQL: Database
- **P**HP: Server-side scripting

---

## ⚙️ Project Structure

```bash
lamp-ansible/
├── ansible.cfg              # Ansible configuration
├── inventory.ini            # Inventory file with EC2 host info
├── playbooks/
│   └── main.yml             # Master playbook
├── roles/
│   ├── apache/
│   │   └── tasks/main.yml   # Apache setup
│   ├── mysql/
│   │   └── tasks/main.yml   # MySQL setup
│   └── php/
│       └── tasks/main.yml   # PHP setup
└── vars/
    └── main.yml             # Variables like MySQL root password


#Features
* SSH-based remote provisining of  an EC2 instance
* Apache installation and service setup
* MySQL secure installation with root password
* PHP installation and apache integration
* Modular roles for easier maintenance

#Technologies Used
* Ansible
* AWS EC2 (Ubuntu 20.04)
* Apache2, MySQL, PHP
* YAML for Playbooks
* SSH for remote connection

#Prerequisites
* AWS account with an Ubuntu EC2 instance
* Security group allowing inbound:
    Port 22 (SSH)
    Port 80 (HTTP)
* Ansible installed on your local machine
* SSH key pair (.pem file) for EC2 access


# How to Run
-Clone the Repository
* git clone https://github.com/your-username/Lamp-Ansible-Project.git
cd Lamp-Ansible
-Update Inventory file
* [web]
ec2-public-ip ansible_user=ubuntu ansible_ssh_private_key_file=~/your-key.pem
- Set Variables[vars/main.yml]
* mysql_root_password: yourpassword
-Run the Playbook
* ansible-playbook -i inventory.ini playbooks/main.yml
-Verify Setup
* Open browser: http://<your-ec2-public-ip>

#What I Learned
* Writing modular Ansible playbooks using roles
* Connecting and provisioning AWS EC2 via SSH
* Automating the entire software stack setup
* Ensuring repeatability and consistency in deployments


