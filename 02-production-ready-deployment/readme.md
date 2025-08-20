# 02 - Production-Ready Deployment

This project demonstrates upgrading the basic EC2 deployment to a **production-ready website** with Elastic IP, domain mapping (GoDaddy + Route 53), and HTTPS (SSL/TLS) via Let's Encrypt.

---

## 🚀 Deployment Steps

### 1️⃣ Configure Elastic IP
- Allocated an **Elastic IP** in AWS.
- Associated it with the EC2 instance.

**Screenshot 1:** Elastic IP Allocation  
<img width="1850" height="840" alt="Screenshot 2025-08-20 165426" src="https://github.com/user-attachments/assets/2ada9123-12ac-4ced-b38f-83af25564ec0" />


---

### 2️⃣ Manage Domain with GoDaddy & Route 53
1. Domain registered with **GoDaddy**.  
2. In GoDaddy DNS Management:
   - Updated **NS (Name Server) records** to point to the Route 53 hosted zone.
3. In **AWS Route 53**:
   - Created a **Hosted Zone** for `balwantdevops.xyz`.
   - Added an **A Record** pointing domain → Elastic IP.

**Screenshot 2:** Route 53 Records & Domain Setup  
<img width="1012" height="670" alt="Screenshot 2025-08-20 165844" src="https://github.com/user-attachments/assets/1932d998-0d64-425c-bd7e-77d8f868eec5" />
<img width="370" height="561" alt="Screenshot 2025-08-20 180037" src="https://github.com/user-attachments/assets/affea8f0-a7b6-41ec-8f3b-8fe08e43f79f" />
<img width="1365" height="887" alt="Screenshot 2025-08-20 171022" src="https://github.com/user-attachments/assets/d1e62fa8-0070-48fb-96da-88a3d8037f7c" />


---

### 3️⃣ Enable HTTPS with Let’s Encrypt

sudo amazon-linux-extras enable epel
sudo yum install -y certbot python2-certbot-apache
sudo certbot --apache -d balwantdevops.xyz -d www.balwantdevops.xyz
<img width="1403" height="654" alt="Screenshot 2025-08-20 182530" src="https://github.com/user-attachments/assets/4dbab721-8b70-42fb-8ae1-22e50ca87ef8" />


---

### 4️⃣ Verify HTTPS Website

Access via https://balwantdevops.xyz

<img width="1919" height="1014" alt="Screenshot 2025-08-20 183500" src="https://github.com/user-attachments/assets/db3ba7af-1a25-470a-b803-b83e3c81a6c2" />


---

###💡 Key Learnings

- Elastic IP ensures stable hosting.

- Integrating an external domain registrar (GoDaddy) with AWS Route 53.

- DNS management and routing domains to AWS servers.

- HTTPS/SSL configuration for secure communication.

- Deploying a production-ready environment on AWS.


---

### 🔜 Next Steps

- Implement Auto Scaling Groups for high availability.

- Integrate Application Load Balancer for fault tolerance.

- Automate deployments with Terraform / EC2 Image Builder.
