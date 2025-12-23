# Student Registration System (Dynamic Web Application)

## 📌 Project Introduction

The **Student Registration System** is a dynamic web-based application developed to collect and store student information using a web form. This project demonstrates the implementation of a simple yet effective **dynamic website** using **Apache Web Server**, **PHP**, and **MariaDB** running on an **AWS EC2 instance**.

The application allows users to register by entering their personal details, which are then securely stored in a database. This project is ideal for understanding server-side scripting, database connectivity, and basic cloud deployment.

---

## 🛠️ Technologies Used

* **Cloud Platform:** AWS EC2 (Amazon Linux 2023)
* **Web Server:** Apache HTTP Server
* **Backend Language:** PHP
* **Database:** MariaDB
* **Frontend:** HTML
* **OS:** Linux



## 🏗️ Project Architecture



![](/photos/9%20photo.jpeg)
---
**Architecture Explanation:**

* The user accesses the registration form through a browser.
* Apache serves the HTML/PHP files.
* PHP processes the form data.
* MariaDB stores student registration details.

---

## 🚀 Project Implementation Steps

### 1️⃣ Launch EC2 Instance

* Created an EC2 instance named **Student-Registration**
* Used **Amazon Linux 2023 AMI**
* Instance type: `t3.micro`
* Configured Security Group to allow:

  * HTTP (Port 80)
  * SSH (Port 22)

![](photos/1%20photo.jpeg)

---

### 2️⃣ Install LEMP, PHP & MariaDB

```bash
sudo yum update -y
sudo yum install nginx mariadb105-server php -y
```

Start services:

```bash
sudo systemctl start nginx mariadb php-fpm
sudo systemctl enable nginx mariadb php-fpm 
```

---

### 3️⃣ Create Student Registration Form

* Created an HTML form with fields:

  * Name
  * Email
  * Website
  * Comment
  * Gender
* Form uses `POST` method and sends data to `submit.php`

### * signup.html
![](photos/2%20photo.jpeg)

### * submit.php
![](photos/3%20photo.jpeg)
---

### 4️⃣ PHP Backend Processing

* PHP file (`submit.php`) collects form data
* Establishes connection with MariaDB
* Inserts student data into database table


---

### 5️⃣ Database Creation (MariaDB)
* sudo mysql 
* set pass- alter user root@localhost by'root'



```sql
CREATE DATABASE student_db;
USE student_db;

CREATE TABLE students (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  website VARCHAR(100),
  comment TEXT,
  gender VARCHAR(10)
);
```
![](photos/4%20photo.jpeg)

---

### 7️⃣ Testing

* Accessed application using:

  ```
  http://<EC2-Public-IP>/signup.html
  ```
  ![](photos/6%20photo.jpeg)

* Filled registration form

![](photos/7%20photo.jpeg)
* Verified data insertion in MariaDB

![](photos/8%20photo.jpeg)

---

## ✅ Project Outcome

* Successfully created a dynamic registration system
* User data stored securely in database
* Application hosted on AWS EC2

---

## 📌 Conclusion

This project helped in understanding the complete flow of a **dynamic web application**, from frontend form creation to backend processing and database storage. It also provided hands-on experience with **Linux server management**, **Apache configuration**, **PHP-MySQL integration**, and **cloud deployment using AWS EC2**. This project is well-suited for **freshers** looking to showcase practical skills in web development and cloud computing.

---

## 🔮 Future Enhancements

* Add form validation using JavaScript
* Implement user authentication
* Improve UI using CSS/Bootstrap
* Deploy using Load Balancer & Auto Scaling

---

## 👨‍💻 Author

**Student Registration System Project**
Developed by a Cloud & Web Development Fresher
