# 🚀 Highly Available Two-Tier Web Application on AWS

## 📌 Project Overview

This project demonstrates the deployment of a **Highly Available Two-Tier Web Application** on **Amazon Web Services (AWS)** using industry-standard cloud architecture.

The application is built with:

* **Frontend:** HTML, CSS, JavaScript
* **Backend:** PHP
* **Web Server:** Apache/Nginx
* **Database:** MySQL (Amazon RDS)

The infrastructure is designed to provide **high availability, scalability, fault tolerance, and secure communication** between application and database layers.

---

# 🏗️ Architecture

```text
                                Internet
                                    │
                                    ▼
                      Application Load Balancer (ALB)
                                    │
                    ┌───────────────┴───────────────┐
                    │                               │
                    ▼                               ▼
           EC2 Instance (AZ-1)              EC2 Instance (AZ-2)
        Apache/Nginx + PHP App          Apache/Nginx + PHP App
                    │                               │
                    └───────────────┬───────────────┘
                                    │
                              Security Group
                                    │
                                    ▼
                         Amazon RDS MySQL Database
                             (Private Subnet)
```

---

# ☁️ AWS Services Used

| Service                    | Purpose                               |
| -------------------------- | ------------------------------------- |
| Amazon VPC                 | Created isolated virtual network      |
| Public Subnets             | Hosted Load Balancer                  |
| Private Subnets            | Hosted Database                       |
| Internet Gateway           | Internet access for public subnet     |
| NAT Gateway                | Internet access for private resources |
| Route Tables               | Controlled network routing            |
| Security Groups            | Firewall for EC2 and RDS              |
| Amazon EC2                 | Hosted PHP Application                |
| Amazon Machine Image (AMI) | Created reusable server image         |
| Launch Template            | Configuration for Auto Scaling        |
| Auto Scaling Group         | Automatically launches EC2 instances  |
| Application Load Balancer  | Distributes incoming traffic          |
| Amazon RDS (MySQL)         | Managed relational database           |
| IAM                        | Secure AWS resource permissions       |

---

# 📂 Project Structure

```
aws-highly-available-2-tier/
│
├── includes/
│   └── db_connect.php
│
├── nginx/
│   └── quickloan.conf
│
├── public/
│   ├── index.html
│   ├── apply.php
│   ├── submit_application.php
│   ├── styles.css
│   └── images/
│
├── architecture/
│   └── architecture-diagram.png
│
├── screenshots/
│   ├── vpc.png
│   ├── subnets.png
│   ├── ec2.png
│   ├── alb.png
│   ├── asg.png
│   ├── rds.png
│   └── website.png
│
├── scripts/
│   └── user-data.sh
│
├── README.md
└── LICENSE
```

---

# ⚙️ Infrastructure Setup

### Network Layer

* Created custom VPC
* Configured Public and Private Subnets
* Attached Internet Gateway
* Configured NAT Gateway
* Created Route Tables
* Configured Security Groups

---

### Compute Layer

* Launched Amazon EC2 instance
* Installed Apache/Nginx
* Installed PHP
* Deployed QuickLoan application
* Verified application functionality
* Created AMI from configured instance

---

### Database Layer

* Created Amazon RDS MySQL
* Configured Database Security Group
* Allowed database access only from EC2 instances
* Connected PHP application to RDS

---

### Scalability

* Created Launch Template
* Used AMI in Launch Template
* Configured Auto Scaling Group
* Configured minimum, desired, and maximum instance capacity

---

### Load Balancing

* Created Application Load Balancer
* Configured Target Group
* Registered Auto Scaling instances
* Enabled health checks

---

# 🔄 Project Workflow

```
User
 │
 ▼
Application Load Balancer
 │
 ▼
Auto Scaling Group
 │
 ├───────────────┐
 │               │
 ▼               ▼
EC2-1         EC2-2
 │               │
 └──────┬────────┘
        │
        ▼
Amazon RDS MySQL
```

---

# 🚀 Features

* High Availability
* Auto Scaling
* Load Balancing
* Secure Database Access
* Multi-AZ Architecture
* Reusable AMI
* Secure Security Groups
* Scalable Infrastructure
* Fault Tolerant Design
* Responsive Web Application

---

# 📋 Deployment Steps

1. Create VPC
2. Create Public & Private Subnets
3. Configure Route Tables
4. Attach Internet Gateway
5. Create NAT Gateway
6. Configure Security Groups
7. Launch EC2 Instance
8. Install Apache/Nginx & PHP
9. Deploy Application
10. Create Amazon RDS MySQL
11. Connect Application to Database
12. Create AMI
13. Create Launch Template
14. Configure Auto Scaling Group
15. Create Target Group
16. Configure Application Load Balancer
17. Test Application
18. Verify High Availability

---

# 🔐 Security Implementation

* Security Groups used as virtual firewalls
* Database deployed in Private Subnet
* HTTP (80) and HTTPS (443) allowed to ALB
* MySQL (3306) accessible only from EC2 Security Group
* IAM used for secure AWS access
* Least-privilege access followed

---

# 📈 Benefits

* High Availability
* Automatic Scaling
* Improved Performance
* Fault Tolerance
* Secure Architecture
* Reduced Downtime
* Easy Maintenance
* Cost Optimization

---

# 🧪 Testing

✔ Application accessible through Application Load Balancer

✔ Database connectivity verified

✔ Auto Scaling launches new instances

✔ Load Balancer health checks passing

✔ Multiple EC2 instances serving traffic successfully

---

# 💡 Challenges Faced

* Configuring Security Groups correctly
* Connecting EC2 with RDS
* Auto Scaling configuration
* Load Balancer health check troubleshooting
* Route Table configuration
* Database connectivity debugging

---

# 📚 Learning Outcomes

Through this project, I gained practical experience in:

* Amazon VPC Networking
* EC2 Deployment
* Security Groups
* IAM
* Amazon RDS
* Application Load Balancer
* Auto Scaling Group
* Launch Templates
* Amazon Machine Images (AMI)
* High Availability Architecture
* Cloud Networking
* Infrastructure Deployment
* AWS Best Practices

---

# 📸 Screenshots

Add screenshots of:

* VPC
* Public & Private Subnets
* Route Tables
* Internet Gateway
* NAT Gateway
* EC2 Instances
* Security Groups
* Amazon RDS
* Target Group
* Application Load Balancer
* Auto Scaling Group
* Website Home Page

---

# 👨‍💻 Author

**Sujal Phadale**

B.Tech Computer Science & Engineering

AWS Cloud Enthusiast

---

# ⭐ If you found this project useful, please consider giving it a Star.
