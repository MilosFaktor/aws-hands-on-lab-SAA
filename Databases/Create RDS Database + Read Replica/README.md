# 🚀 Hands-On AWS Project – RDS Cross-Region Read Replica

As part of my AWS Solutions Architect Associate course in April, I built and tested a **cross-region RDS read replica** setup using MySQL.

---

## ✅ What I Built

- Launched a **primary RDS MySQL database** (single AZ) in **eu-north-1** (Stockholm)  
- Created a **read replica** of the primary DB in **eu-central-1** (Frankfurt)  
- **Promoted** the read replica to become a standalone writable database  
- **Deleted** the replica after testing  
- Connected to the primary DB using **MySQL Workbench** through its endpoint  
- Configured **security groups** to allow inbound traffic on **port 3306**  
- Enabled **public connectivity** for easier database access during testing

---

## 🧪 Tools & Setup

### Security Configuration
- **Security Group Ingress Rule**: Allowed MySQL/Aurora traffic (`TCP 3306`) from my IP  
- **Public Access**: Temporarily set the DB to be publicly accessible for connection testing

### Database Client
- **MySQL Workbench** for querying and verifying data replication

---

## 📌 Key Learnings

- **Cross-region read replicas** provide disaster recovery and geo-distributed read performance  
- **Promotion of read replicas** allows them to become independent writable instances  
- Proper **security group rules** and **public access settings** are required for external DB tools (e.g., Workbench)  
- **RDS endpoints** for primary vs. replica are separate and must be tracked

---

## 📁 Files Included

- *No code files – all steps performed via AWS Console and MySQL Workbench*  
- [Screenshots](Screenshots/) – optional visual proof of cross-region replication and promotion  

---

## 🔗 Related Links

- [Main Hands-On Repo (aws-hands-on-lab-SAA)](https://github.com/MilosFaktor/aws-hands-on-lab-SAA)

---

## 🏷️ Tags

`#AWS` `#RDS` `#MySQL` `#CrossRegionReplication` `#HandsOnCloud` `#SolutionArchitect` `#AWSCertified` `#Database`
