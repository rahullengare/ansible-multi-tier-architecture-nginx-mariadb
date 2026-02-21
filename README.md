# ansible-multi-tier-architecture-nginx-mariadb
This project automates the deployment of a two-tier architecture using Ansible, configuring Nginx and PHP as the web server and MariaDB as the database server on AWS EC2.

This project demonstrates how to deploy a **2-tier architecture** using Ansible:

- 🌐 Web Server (Nginx + PHP)
- 🛢 Database Server (MariaDB)

The setup is fully automated using an Ansible playbook.

---

## 📌 Project Architecture

Web Server (172.31.25.4)
        |
        |
Database Server (172.31.21.213)

---
## 🛠 Technologies Used

- **Ansible** – Automation tool used to provision and configure servers.
- **Nginx** – Web server used to host the application.
- **PHP** – Server-side scripting language for dynamic web content.
- **MariaDB** – Database server used to manage application data.
- **Amazon Linux 2023** – Operating system running on EC2 instances.
- **AWS EC2** – Cloud compute service used to host web and database servers.


---

## 📋 Inventory File (inventory.ini)

```ini
[webserver]
172.31.25.4

[dbserver]
172.31.21.213

[all:vars]
ansible_user=ec2-user
ansible_ssh_private_key_file=/root/pem-server-key.pem

```

---

## 📜 Playbook Features

### 🔹 Web Server Tasks
- Install Nginx
- Install PHP & PHP-FPM
- Start and enable services
- Deploy custom HTML page

### 🔹 Database Server Tasks
- Install MariaDB 10.5
- Start and enable MariaDB service
- Create a database (`mydatabase`)

---

## ▶️ How to Run the Project

### Step 1: Clone the Repository

```
git clone <your-repo-url>
cd <repo-folder>
```

### Step 2: Run Ansible Playbook

```
ansible-playbook -i inventory.ini playbook.yml
```

---

## 🌐 Web Server Output

Open in browser:

```
http://<web-server-public-ip>
```

You will see:

```
Welcome to Ansible which is running on <server-ip>
```

---

## 🛢 Verify Database

Login to DB server:

```
mysql -u root
```

Check databases:

```
SHOW DATABASES;
```

You should see:

```
mydatabase
```

---

