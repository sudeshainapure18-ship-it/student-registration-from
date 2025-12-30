# Student Registration System (Dynamic Web Application)

## Project Introduction

The **Student Registration System** is a dynamic web-based application developed to collect and store student information using a web form. This project demonstrates the implementation of a simple yet effective **dynamic website** using **Apache Web Server**, **PHP**, and **MariaDB** running on an **AWS EC2 instance**.

The application allows users to register by entering their personal details, which are then securely stored in a database. This project is ideal for understanding server-side scripting, database connectivity, and basic cloud deployment.

---

##  Technologies Used

* **Cloud Platform:** AWS EC2 (Amazon Linux 2023)
* **Web Server:** Apache HTTP Server
* **Backend Language:** PHP
* **Database:** MariaDB
* **Frontend:** HTML
* **OS:** Linux



##  Project Architecture

![9 photo](https://github.com/user-attachments/assets/a469f2d4-03ae-45f2-8f49-5d48eb15445b)




![](/photos/9%20photo.jpeg)
---
**Architecture Explanation:**

* The user accesses the registration form through a browser.
* Apache serves the HTML/PHP files.
* PHP processes the form data.
* MariaDB stores student registration details.

---

##  Project Implementation Steps

###  Launch EC2 Instance

* Created an EC2 instance named **Student-Registration**
* Used **Amazon Linux 2023 AMI**
* Instance type: `t3.micro`
* Configured Security Group to allow:

  * HTTP (Port 80)
  * SSH (Port 22)

![1 photo](https://github.com/user-attachments/assets/e0360e2e-b0df-4fa9-a2e4-84743f1da300)


---

###  Install LEMP, PHP & MariaDB

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

###  Create Student Registration Form

* Created an HTML form with fields:

  * Name
  * Email
  * Website
  * Comment
  * Gender
* Form uses `POST` method and sends data to `submit.php`

### * signup.html
![2 photo](https://github.com/user-attachments/assets/f8839c84-661b-4725-aa8c-7393f314b842)


### * submit.php
![3 photo](https://github.com/user-attachments/assets/3ef2625c-0b23-451c-b5be-d95c9964df5a)

---

### PHP Backend Processing

* PHP file (`submit.php`) collects form data
* Establishes connection with MariaDB
* Inserts student data into database table


---

### Database Creation (MariaDB)
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
![4 photo](https://github.com/user-attachments/assets/48867ccb-40cc-4a51-bd42-8627a2f0a9e8)


---

### Testing

* Accessed application using:

  ```
  http://<EC2-Public-IP>/signup.html
  ```
![6 photo](https://github.com/user-attachments/assets/ecc4d5ea-1594-4565-aff2-b3be529e408a)



* Filled registration form

![7 photo](https://github.com/user-attachments/assets/969eed9f-f53b-40b9-866f-0d08bec28698)


* Verified data insertion in MariaDB

![8 photo](https://github.com/user-attachments/assets/cfde9410-9a6e-4fbc-b790-3cbf4aae4070)


---

##  Project Outcome

* Successfully created a dynamic registration system
* User data stored securely in database
* Application hosted on AWS EC2

---

## Conclusion

This project helped in understanding the complete flow of a **dynamic web application**, from frontend form creation to backend processing and database storage. It also provided hands-on experience with **Linux server management**, **Apache configuration**, **PHP-MySQL integration**, and **cloud deployment using AWS EC2**. This project is well-suited for **freshers** looking to showcase practical skills in web development and cloud computing.

---

##  Future Enhancements

* Add form validation using JavaScript
* Implement user authentication
* Improve UI using CSS/Bootstrap
* Deploy using Load Balancer & Auto Scaling

---

## Author
sudesh ainapure

**Student Registration System Project**
Developed by a Cloud & Web Development Fresher
