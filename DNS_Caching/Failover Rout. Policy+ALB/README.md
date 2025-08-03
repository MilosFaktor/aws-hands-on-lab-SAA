# 🚀 Hands-On AWS Project – Global ALB Failover with Route 53 + CloudFormation

This project demonstrates how to build a **high-availability, cross-region failover system** using **Amazon Route 53**, **ALBs in two AWS regions**, and **CloudFormation**. The system detects failure in one region and automatically redirects traffic to the secondary region using Route 53 health checks and failover routing policies.

---

## ✅ What I Built

- Created **two CloudFormation stacks**, one per region (`eu-north-1` and `eu-central-1`)
- Each stack includes:
  - **Application Load Balancer (ALB)**
  - **Launch Template**
  - **Auto Scaling Group** launching 2 EC2 instances (in 2 subnets / AZs)
  - ALB Listener and Target Group
- Configured a **Route 53 hosted zone** for the domain `cloudnecessities.com`
  - Created **two A records** using **failover routing**:
    - **Primary** → ALB in `eu-north-1`
    - **Secondary** → ALB in `eu-central-1`
- Added **Route 53 health checks** for both ALBs
  - Health check monitors the primary ALB
  - If it becomes unhealthy, traffic is routed to the secondary ALB

---

## 🌍 Failover Test Logic

1. Accessed the domain:  
   ➤ Browser returned instance page from `eu-north-1a` or `eu-north-1c`  
   ➤ Confirmed traffic is hitting the **primary region**

2. Simulated failure (e.g., stopped EC2 or failed health check)

3. Accessed the domain again:  
   ➤ Now served content from `eu-central-1a` or `eu-central-1c`  
   ➤ Confirmed **failover to the secondary ALB** is working

✅ This proves that DNS-based global failover using Route 53 is correctly configured.

---

## 🧪 Setup Overview

### 📦 Stack Deployment (per region)
- Used the same [`alb-cf-template.yml`](alb-cf-template.yml) to launch resources in both regions
- Auto Scaling group spread EC2s across two subnets for availability
- ALB handled incoming traffic via HTTP and forwarded to EC2s

### 🌐 Route 53 Configuration
- Hosted Zone: `cloudnecessities.com`
- A Record 1:  
  - Alias to **Primary ALB**
  - Failover type: **Primary**
  - Associated with **Health Check 1**
- A Record 2:  
  - Alias to **Secondary ALB**
  - Failover type: **Secondary**
  - Associated with **Health Check 2**

### 📡 Health Checks
- Created for each ALB DNS name (dualstack)
- Enabled health evaluations to control failover logic

---

## 🖼️ Screenshots

## 🖼️ Screenshots

- [CloudFormation stack created in `eu-north-1`](Screenshots/1 - stack created in primary region.png)
- [CloudFormation stack created in `eu-central-1`](Screenshots/2 - stack created in secondary region.png)
- [Route 53 hosted zone with failover A records](Screenshots/3 - Records in hosted zone for failover.png)
- [Route 53 health checks linked to primary and secondary ALBs](Screenshots/4 - Health checks.png)
- [Website response served from AZ `eu-north-1a`](Screenshots/5 - Primary eu-north-1a.png)
- [Website response served from AZ `eu-north-1c`](Screenshots/6 - Primary eu-north-1c.png)
- [Simulated failure: primary ALB marked unhealthy](Screenshots/7 - testing failure and primary is unhealthy.png)
- [Website response rerouted to AZ `eu-central-1c`](Screenshots/8 - secondary eu-central-1c.png)
- [Website response rerouted to AZ `eu-central-1a`](Screenshots/9 - secondary eu-central-1a.png)

---

## 📁 Files Included

- [`alb-cf-template.yml`](alb-cf-template.yml) – CloudFormation template used for both regions
- [Screenshots folder](Screenshots/) – Evidence of configuration and failover

---

## 📌 Key Learnings

- How to use **CloudFormation** for multi-region deployment
- Implementing **Route 53 failover routing policies**
- Creating and associating **Route 53 health checks**
- Using **ALB and EC2 across availability zones** for high availability
- Verifying real-world failover by observing DNS redirection and AZ responses

---

## 🔗 Related Links

[Main Hands-On Repo (aws-hands-on-lab-SAA)](https://github.com/MilosFaktor/aws-hands-on-lab-SAA)

---

## 🏷️ Tags

#AWS #Route53 #Failover #ALB #EC2 #MultiRegion #CloudFormation #HighAvailability #HandsOnCloud #AWSProjects #DNS #SolutionArchitect #AWSCertified
