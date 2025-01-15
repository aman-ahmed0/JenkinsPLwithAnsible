# JenkinsPLwithAnsible
Install Docker and Docker-Compose with Ansible in Jenkins Pipeline using Ansible. Docker and Docker-Compose may be used for further installations when needed.
You should have configured Jenkins to use the branch where you have the files (prepare_ansible_server.sh), Jenkins file, and the Ansible folder.

# DevOps Automation with Ansible, Jenkins, and Docker

This repository demonstrates my expertise in **DevOps automation** using **Ansible**, **Jenkins**, and **Docker**. The project showcases how to automate infrastructure provisioning, configuration management, and deployment workflows.

---

## **Technologies Used**
- **Ansible**: For configuration management and automation.
- **Jenkins**: For CI/CD pipeline orchestration.
- **Docker**: For containerization and application deployment.
- **AWS EC2**: For cloud infrastructure provisioning.
- **NGINX**: As a web server for demonstration purposes.

---

## **Project Overview**
This project includes the following components:

1. **Ansible Playbooks**:
   - Automates the installation and configuration of:
     - Python3, Docker, and Docker Compose.
     - NGINX web server (optional).
   - Uses dynamic inventory with AWS EC2 instances.

2. **Jenkins Pipeline**:
   - Automates the deployment process by:
     - Copying necessary files to the Ansible control node.
     - Executing Ansible playbooks to configure EC2 instances.

3. **Docker Integration**:
   - Installs Docker and Docker Compose on target servers.
   - Prepares the environment for containerized applications.

---

## **Files in the Repository**

### **1. `prepare_ansible_server.sh`**
- A Bash script to prepare the Ansible control node.
- Installs Ansible, Python3, and required Python libraries (e.g., `boto3`, `botocore`).

### **2. `myPlaybook.yaml`**
- Ansible playbook to:
  - Install Python3, Docker, and Docker Compose.
  - Start the Docker daemon.
  - Install the Docker Python module.
  - Configure NGINX (optional).

### **3. `inventory_aws_ec2.yaml`**
- Dynamic inventory script for AWS EC2 instances.
- Groups instances by tags and instance types.

### **4. `ansible.cfg`**
- Ansible configuration file:
  - Disables host key checking.
  - Specifies the dynamic inventory and Python interpreter.
  - Configures remote user and private key for AWS EC2 instances.

### **5. Jenkins Pipeline (`Jenkinsfile`)**
- A Jenkins pipeline to:
  - Copy files to the Ansible control node.
  - Execute the Ansible playbook to configure EC2 instances.

---

## **How to Use This Repository**

### **Prerequisites**
- An AWS account with EC2 instances.
- Jenkins server with SSH agent and credentials configured.
- Ansible installed on the control node.

### **Steps to Run the Project**
1. **Prepare the Ansible Control Node**:
   - Run the `prepare_ansible_server.sh` script to install Ansible and dependencies.
   ```bash
   chmod +x prepare_ansible_server.sh
   ./prepare_ansible_server.sh