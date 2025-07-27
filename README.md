# WordPress-on-EC2
Project to deploy and monitor a WordPress site using AWS EC2 and CloudWatch
# 🖥️ AWS WordPress Deployment (Static EC2 + Security + SSL)

## 📌 Project Summary
This project demonstrates how to deploy a secure WordPress site using a pre-configured Bitnami WordPress AMI on an AWS EC2 instance. It includes configuring security groups, SSH access, and HTTPS encryption using Let's Encrypt.

## 🎯 Objectives
- Launch a WordPress website using EC2 and Bitnami
- Configure SSH access securely with a key pair
- Retrieve and use WordPress admin credentials
- Install SSL certificate via `bncert-tool`
- Document troubleshooting steps and solutions

---

## 🛠️ Tech Stack
| Service | Purpose |
|--------|---------|
| **AWS EC2** | Host the WordPress instance |
| **Bitnami WordPress AMI** | Pre-configured LAMP + WordPress stack |
| **IAM & SSH** | Secure access to EC2 |
| **Security Groups** | Manage allowed inbound traffic (22, 80, 443) |
| **Let's Encrypt / Certbot** | Free SSL certificate |
| **Route 53 (optional)** | Custom domain setup |

---

## 🪜 Setup Instructions

### Step 1: Launch EC2 with Bitnami AMI
- Use AWS Marketplace > Bitnami WordPress Certified by Bitnami and Automattic
- Select t2.micro (free tier)
- Assign a key pair (download `.pem` file)
- Open ports 22 (SSH), 80 (HTTP), 443 (HTTPS)

### Step 2: SSH Into Instance
```bash
chmod 400 your-key.pem
ssh -i your-key.pem bitnami@<your-ec2-public-ip>
