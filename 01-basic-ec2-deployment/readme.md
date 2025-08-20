# 01 - Basic EC2 Deployment

This project demonstrates my first step in deploying a portfolio website on **AWS EC2 (Amazon Linux)** and integrating it with GitHub for version control.

---

## 🚀 Deployment Steps

### 1️⃣ Launch EC2 Instance
- Selected **Amazon Linux 2** (t2.micro, Free Tier) via AWS Console.
- Configured **Security Group**:
  - HTTP (port 80)
  - SSH (port 22)

**Screenshot 1:** EC2 Dashboard  

<img width="1439" height="728" alt="Screenshot 2025-08-19 135648" src="https://github.com/user-attachments/assets/df1a0dc4-a340-4761-aab4-f633223dcc41" />


---

### 2️⃣ Connect via SSH
- Connected to EC2 using SSH:
ssh -i "your-key.pem" ec2-user@<public-ip>
<img width="1168" height="636" alt="Screenshot 2025-08-19 140530" src="https://github.com/user-attachments/assets/295a2178-c9c6-46f8-869a-ac29f0c1fa95" />


---

### 3️⃣ Install Apache Web Server

sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd

<img width="1752" height="682" alt="Screenshot 2025-08-19 1417340" src="https://github.com/user-attachments/assets/e1a287d0-c9fb-425a-8bc5-e308bc038d08" />

---

### 4️⃣ Clone Website from GitHub
- cd /var/www/html
 - sudo git clone https://github.com/balwant2711/<your-portfolio-repo>.git .
<img width="1294" height="251" alt="Screenshot 2025-08-19 141734" src="https://github.com/user-attachments/assets/dcb47041-7966-4682-9e8b-767bd8d3139c" />


---

### 5️⃣ Verify Deployment

- Access site via public IP: http://<your-public-ip>

<img width="1439" height="808" alt="Screenshot 2025-08-19 142132" src="https://github.com/user-attachments/assets/00853188-3d43-4265-9734-b373bd45853d" />


---

### 💡 Key Learnings

- Launching and configuring AWS EC2 instance.

- Installing and managing Apache HTTP server.

- Deploying website files via GitHub clone.

- Hands-on experience bridging coding → cloud deployment.


---

### 🔜 Next Steps

- Configure Elastic IP for stable hosting.

- Map a custom domain using Route 53.

- Enable HTTPS/SSL for secure access.


