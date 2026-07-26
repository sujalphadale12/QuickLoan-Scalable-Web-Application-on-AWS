# QuickLoan – Scalable 2-Tier Web Application on AWS

QuickLoan is a cloud-native web application built using PHP, HTML, CSS, JavaScript, and Nginx. This project demonstrates a highly available, fault-tolerant, and auto-scaling 2-tier architecture deployed on Amazon Web Services (AWS).

---

## 🏗️ Architecture Overview

The application is deployed inside a custom Virtual Private Cloud (VPC) spanning multiple Availability Zones (AZs) to ensure high availability and zero single points of failure.

```text
                  [ Internet / Clients ]
                            │
                            ▼
             [ Internet Gateway (IGW) ]
                            │
    ┌───────────────────────┴───────────────────────┐
    │                Public Subnets                 │
    │     [ Application Load Balancer (ALB) ]      │
    └───────────────────────┬───────────────────────┘
                            │
    ┌───────────────────────┼───────────────────────┐
    │                Private Subnets                │
    │                       │                       │
    │      ┌────────────────┴────────────────┐      │
    │      │  Auto Scaling Group (EC2)       │      │
    │      │  (Nginx + PHP-FPM App Layer)    │      │
    │      └────────────────┬────────────────┘      │
    │                       │                       │
    │      ┌────────────────┴────────────────┐      │
    │      │    Amazon RDS (MySQL Engine)    │      │
    │      └─────────────────────────────────┘      │
    └───────────────────────────────────────────────┘
⚙️ Key Technical Features & AWS Services

    Custom VPC Infrastructure: Configured Public & Private Subnets across 2 Availability Zones with custom Route Tables and Internet Gateway.

    Nginx + PHP-FPM Stack: Efficient handling of static assets and dynamic PHP execution via Nginx fastcgi processing.

    Database Isolation: Amazon RDS MySQL placed in private subnets with restricted Security Groups.

    Golden AMI & Auto Scaling: Base EC2 instance configured with Nginx, PHP, and code, captured into a custom AMI for launch templates and dynamic Auto Scaling.

    Traffic Distribution: Application Load Balancer (ALB) routes public incoming traffic across active EC2 targets.

    Security Hardening: Enforced Principle of Least Privilege across all Security Groups; sensitive files excluded via .gitignore.

🚀 Local Setup & Deployment

    Database Configuration:
    Bash

    cp includes/db_connect.php.example includes/db_connect.php

    Update includes/db_connect.php with your RDS Endpoint, MySQL username, database name, and password.

    Nginx Configuration:
    Copy nginx/quickloan.conf to your server's Nginx configuration directory:
    Bash

    sudo cp nginx/quickloan.conf /etc/nginx/conf.d/
    sudo systemctl restart nginx

🧪 Testing & Verification

    Load Balancing: Verified ALB distribution by analyzing web access logs across multiple EC2 targets.

    Auto Healing: Simulated instance failure in the Auto Scaling Group; ASG automatically replaced terminated nodes.

    End-to-End Submission: Verified form submissions on apply.php writing records into Amazon RDS MySQL.
    EOF
