# 🔌 Hands-On AWS Project – Elastic Network Interfaces (ENIs) and Multi-Subnet EC2 Setup

This project demonstrates how to attach multiple **Elastic Network Interfaces (ENIs)** to an EC2 instance, assign it multiple private IPs, and place it across **two different subnets**. It was completed as part of my AWS Solutions Architect Associate course in April.

---

## ✅ What I Built

- Launched a single **EC2 instance** with:
  - **2 ENIs** (Elastic Network Interfaces)
  - Each ENI placed in a **different subnet**
  - Each ENI assigned a **separate private IP**
- Attached an **Elastic IP** to one of the ENIs
- Applied **Security Groups** at the **ENI level** (not just instance level)

---

## 🔧 Key Configuration Details

- **ENI = the binding point between EC2 and a Subnet**
  - Each ENI is bound to a specific subnet
  - An EC2 can connect to multiple subnets using multiple ENIs

- **Elastic IP** was attached to the **primary ENI** to allow external access

- **Security Groups** were attached directly to each ENI:
  - Enables **fine-grained traffic control** per interface

---

## 🧠 Key Learnings

- EC2 instances can have **multiple network interfaces**, each in **different subnets**
- ENIs are the component that **connect an EC2 to a specific subnet**
- **Elastic IPs attach to ENIs**, not directly to instances
- Security Groups can be **configured per ENI**, enabling segmented traffic rules

---

## 📁 Files Included

- `README.md` – This documentation
- [EC2 instance with 2 ENIs, each in a separate subnet](Screenshots/Screenshot%202025-03-24%20173858.png)

---

## 🔗 Related Links

[Main Hands-On Repo (aws-hands-on-lab-SAA)](https://github.com/MilosFaktor/aws-hands-on-lab-SAA)

---

## 🏷️ Tags

#AWS #ENI #EC2 #ElasticIP #Subnets #Networking #SecurityGroups #HandsOnCloud #AWSProjects #SolutionArchitect #AWSCertified
