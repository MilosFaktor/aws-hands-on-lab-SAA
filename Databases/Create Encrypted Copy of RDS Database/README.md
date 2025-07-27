# 🚀 Hands-On AWS Project – RDS Snapshot Encryption & Restore Workflow

As part of my AWS Solutions Architect Associate course in April, I tested how to securely create and work with **encrypted RDS databases** using snapshots and AWS Key Management Service (KMS).

---

## ✅ What I Built

- Created an **unencrypted RDS database**  
- **Populated the database** with sample data  
- Created a **manual unencrypted snapshot** of the DB  
- Used **"Copy Snapshot"** to create an **encrypted copy** using the default AWS KMS key  
- **Restored** a new RDS instance from the encrypted snapshot  
- **Queried** the new encrypted DB to confirm that data and functionality were preserved

---

## 🔐 Key Learnings

- RDS **snapshots can be encrypted** only during the copy process  
- You **cannot decrypt** an encrypted snapshot — encryption is one-way and permanent  
- When you **restore from an encrypted snapshot**, the new DB is also encrypted  
- This workflow is useful to **upgrade legacy unencrypted databases** without downtime  
- KMS keys (default or customer-managed) are required for encryption  
- IAM roles and KMS permissions must allow encryption actions for this to work smoothly

---


## 📁 Files Included

- *No code files for this lab – all steps were performed via AWS Console*
- [Screenshots](Screenshots/) – optional visual proof of each step

---

## 🔗 Related Links

- [Main Hands-On Repo (aws-hands-on-lab-SAA)](https://github.com/MilosFaktor/aws-hands-on-lab-SAA)

---

## 🏷️ Tags

`#AWS` `#RDS` `#Encryption` `#Snapshots` `#HandsOnCloud` `#KMS` `#SolutionArchitect` `#AWSCertified`
