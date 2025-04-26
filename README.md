
# **Database Management with AWS RDS**  

## **Table of Contents**  
1. [Project Overview](#1-project-overview)  
2. [Objectives](#2-objectives)  
3. [Database Management with AWS RDS](#3-creating-the-database-in-aws-rds)  
   - [Navigating to RDS](#31-navigate-to-rds)  
   - [Creating a New Database](#32-create-a-new-database)  
   - [Configuring Database Settings](#33-configure-database-settings)  
4. [Setting Up an EC2 Instance for RDS Connection](#4-setting-up-an-ec2-instance-for-rds-connection)  
5. [Troubleshooting (Common Issues and Solutions)](#5-troubleshooting-common-issues-and-solutions)  
6. [Conclusion](#6-conclusion)  

---

## **1. Project Overview**  

In cloud-based applications, managing relational databases efficiently is essential for scalability, reliability, and security. This capstone project demonstrates the **deployment, configuration, and integration of an AWS RDS MySQL instance** with an EC2 server.  

Through this project, you will learn how to:  
✅ Set up an AWS RDS database from scratch.  
✅ Configure network security settings for seamless EC2-RDS communication.  
✅ Troubleshoot common database connection errors.  
✅ Optimize database settings for better performance and security.  

By following this guide, you will build a **production-ready database setup** that can be used for web applications, analytics, and other cloud-based workloads.  

---

## **2. Objectives**  

The primary objectives of this project include:  

### **Technical Goals**  
✔️ **Deploy an AWS RDS instance** with MySQL.  
✔️ **Configure database security settings** (VPC, Subnet Groups, Security Groups).  
✔️ **Enable EC2-RDS communication** and install the MySQL client.  
✔️ **Connect an EC2 instance to RDS** using MySQL CLI.  
✔️ **Implement authentication best practices** to secure database access.  
✔️ **Troubleshoot common AWS RDS issues** (network, authentication, security settings).  

### **Performance and Security Enhancements**  
✔️ **Enable Multi-AZ Deployment** (High Availability).  
✔️ **Configure automated backups and snapshots** for data safety.  
✔️ **Monitor RDS performance** using AWS CloudWatch.  
✔️ **Optimize database queries** for better efficiency.  

---

---

# 3. Database Management with AWS RDS

## 3.1. Creating the Database

### Step 1: Navigate to RDS  
Search for **RDS** in the AWS search bar.  

![RDS Search](https://github.com/user-attachments/assets/ec39d2f3-a9db-4827-a544-2031354ed230)  

### Step 2: Open the Database Section  
Click on the **Databases** option in the RDS dashboard.  

![Database Section](https://github.com/user-attachments/assets/de8d1dc4-9a23-4d5f-b530-f28dfc1268ae)  

### Step 3: Create a New Database  
Click on the **Create database** button.  

![Create Database](https://github.com/user-attachments/assets/cd9369f9-0a71-4f43-97e7-bd955436078d)  

### Step 4: Choose Standard Create  
Select **Standard create** to manually configure database settings.  

![Standard Create](https://github.com/user-attachments/assets/5d8074fb-5c9d-4ad4-9420-b302b98e1846)  

### Step 5: Select MySQL Engine Type  
Choose **MySQL** as the database engine.  

![MySQL Engine](https://github.com/user-attachments/assets/bd928400-82a3-4d87-9c75-d38cf764d7b4)  

### Step 6: Select MySQL Engine Version  
For this guide, we are using **MySQL 8.0.35**.  

![MySQL 8.0.35](https://github.com/user-attachments/assets/2f7f471d-3127-4c11-8ab4-971b7ae737a1)  

### Step 7: Choose Free Tier Template  
For cost-saving, select the **Free Tier** template.  

![Free Tier Template](https://github.com/user-attachments/assets/7205b1fc-09f2-4964-995a-3c3b42c6b7a3)  

### Step 8: Enter Database Name  
Provide a name for your database.  

![Database Name](https://github.com/user-attachments/assets/a6527729-74f4-40c4-a3c7-9f83987250aa)  

### Step 9: Set Master Password  
Enter and save your **Master Password** for future access.  

![Master Password](https://github.com/user-attachments/assets/ef53c337-d606-4e01-a1d3-80529f021757)  

### Step 10: Select Existing VPC  
Choose an existing **VPC** with multiple availability zones.  

![VPC Selection](https://github.com/user-attachments/assets/7719034a-6491-4f99-8887-a8e6f4f562e8)  

### Step 11: Enable Public Access  
Ensure that your database is publicly accessible.  

![Public Access](https://github.com/user-attachments/assets/df8d6ca8-fe99-4609-9583-63eaa703dd5a)  

### Step 12: Configure Security Group  
Select a **Security Group** that allows inbound traffic on port **3306**.  

![Security Group](https://github.com/user-attachments/assets/4f9afb6a-bd8f-4f3c-aa3f-feddaf8affb1)  

### Step 13: Verify Database Settings  
Ensure your database configuration matches the expected settings.  

![Database Configuration](https://github.com/user-attachments/assets/ee7313b5-020a-41d0-b5a5-7f9022d36566)  

### Step 14: Choose Availability Zone  
Select an appropriate **Availability Zone** for the database.  

![Availability Zone](https://github.com/user-attachments/assets/6cf18cc2-0e71-4a2b-a3af-1304f3dc89e1)  

### Step 15: Select Database Authentication  
Choose **Password Authentication** as the login method.  

![Password Authentication](https://github.com/user-attachments/assets/c1534ef0-e991-4b79-baf6-4e91bff536d9)  

### Step 16: Create the Database  
Click on **Create Database** to finalize the setup.  

![Database Created](https://github.com/user-attachments/assets/2f82b320-c4ac-4c3f-8c2b-f6ac5aff1239)  

---

## 4. Setting Up the EC2 for RDS  

### Step 1: SSH into the EC2 Instance  
Log in to your **EC2 instance** using SSH.  

![SSH Access](https://github.com/user-attachments/assets/d45d8173-a995-4a3e-9792-d5cefe7dd49c)  

### Step 2: Download MySQL Client  
Install the **MySQL client package** on the EC2 instance.  

![Download MySQL Client](https://github.com/user-attachments/assets/42ebec0d-4fb1-400d-95ba-69829acd5214)  

### Step 3: Verify the Downloaded Package  
Ensure the package is successfully downloaded.  

![Downloaded Package](https://github.com/user-attachments/assets/1b1d6be0-0612-4e9f-8cbb-eada7180abbe)  

### Step 4: Update Server OS  
Run a system update before installing MySQL.  

![Update OS](https://github.com/user-attachments/assets/2a4e937d-7794-4fe1-8c49-42b489849abb)  

### Step 5: Install MySQL Client  
Execute the installation command.  

![Install MySQL Client](https://github.com/user-attachments/assets/7bc2afb2-29a9-409e-a5bb-a290eb09e776)  

### Step 6: Verify Installation  
Confirm MySQL was installed successfully.  

![Installation Complete](https://github.com/user-attachments/assets/ff64e5d5-2310-4340-a50e-ef7064e50ed0)  

### Step 7: Check MySQL Version  
Ensure MySQL client is running properly.  

![Check MySQL Version](https://github.com/user-attachments/assets/075045b7-07b4-4aa9-862d-e730c4171bd9)  

### Step 8: Start MySQL Service  
Enable MySQL to start automatically.  

![Enable MySQL Service](https://github.com/user-attachments/assets/6bcfd3bb-c64c-4a89-b4dc-370a63f869cb)  

### Step 9: Connect EC2 to RDS  
Use the MySQL client to connect to your **AWS RDS database**.  

![Connect to RDS](https://github.com/user-attachments/assets/ef84a61b-ca0f-4b2e-8c9f-b4dacf28e042)  

### Step 10: Enter Password and Access MySQL  
Enter your **database password** when prompted, and verify MySQL is launched.  

![MySQL Connection Success](https://github.com/user-attachments/assets/23f2f153-8f71-448a-a366-68eff1a6898a)  

---
---
## **5. Troubleshooting (Common Issues and Solutions)**  

### **5.1. Connection Errors**  

**Problem:**  
- "Can’t connect to MySQL server (ERROR 2003 or Access Denied)."  

**Solutions:**  
1. Verify credentials:  
   ```bash
   mysql -h [HOST] -u [USER] -p
   ```
2. Check MySQL service status:  
   ```bash
   sudo systemctl status mysql
   sudo systemctl restart mysql
   ```
3. Ensure Security Group allows **port 3306** access.  

### **5.2. Authentication Plugin Error**  

**Problem:**  
- "Client does not support authentication protocol (caching_sha2_password error)."  

**Solution:**  
Switch authentication method:  
```sql
ALTER USER 'your_user'@'%' IDENTIFIED WITH mysql_native_password BY 'your_password';
FLUSH PRIVILEGES;
```

---

## **6. Conclusion**  

This capstone project covers the entire lifecycle of **deploying, securing, and managing an AWS RDS MySQL database**. From configuring network settings to troubleshooting authentication issues, you have successfully implemented a **cloud-based relational database** for production-level applications.  

With the knowledge gained from this project, you can:  
✔️ Set up AWS RDS instances for real-world applications.  
✔️ Improve security with best practices.  
✔️ Monitor and optimize database performance.  
✔️ Integrate RDS with cloud-based applications and analytics.  


---
