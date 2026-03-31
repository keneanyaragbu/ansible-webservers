# Automated Web Server Provisioning with Ansible & AWS EC2

## Project Overview
This project demonstrates the use of Ansible to automatically provision 
and configure Nginx web servers on AWS EC2 instances from scratch. 
It covers core DevOps concepts including configuration management, 
infrastructure automation, security hardening, and dynamic 
configuration file generation using Jinja2 templates.

## Architecture
- 1 Ansible Control Node (EC2)
- 2 Managed Worker Nodes (EC2)
- All instances running on AWS (Amazon Linux 2)

## Technologies Used
- Ansible
- AWS EC2
- Nginx
- Jinja2 Templates
- firewalld
- Git & GitHub

## What This Project Does
- Installs and configures Nginx web server on multiple EC2 instances
- Deploys a custom webpage dynamically using Ansible
- Creates a Linux user on managed nodes
- Hardens servers using firewalld (allows HTTP, restricts unnecessary ports)
- Generates dynamic configuration files using Jinja2 templates
- Manages SSH key authentication between control and worker nodes

## Security Best Practices Applied
- SSH access on worker nodes restricted to control node private IP only
- Firewall configured at OS level using firewalld
- AWS Security Groups configured following principle of least privilege
- Private IPs used for internal EC2 communication

## Project Structure
ansible-webservers/
├── inventory.ini        # Defines managed nodes
├── webservers.yaml      # Main Ansible playbook
├── app.conf.j2          # Jinja2 configuration template
└── README.md            # Project documentation

## How to Run
1. Clone this repository
2. Update inventory.ini with your EC2 instance IPs
3. Ensure your SSH key is available at ~/.ssh/key.pem
4. Test connectivity:
ansible -i inventory.ini webservers -m ping
5. Run the playbook:
ansible-playbook -i inventory.ini webservers.yaml

## Key Concepts To Learned
- Ansible playbooks and inventory management
- YAML syntax and structure
- Jinja2 templating for dynamic config generation
- AWS EC2 security groups and network hardening
- firewalld configuration via Ansible
- Git version control and GitHub project management

## Author
Anyaragbu Kenechukwu Nnaemeka
www.linkedin.com/in/kenechukwu-anyaragbu
