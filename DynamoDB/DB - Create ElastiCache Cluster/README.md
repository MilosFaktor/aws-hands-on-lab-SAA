# 🚀 Hands-On AWS Project – ElastiCache Redis Integration via EC2

In this project, I tested how to interact with **Amazon ElastiCache for Redis** by launching an EC2 instance, installing Python and Redis client tools, and running a simple script to populate and retrieve values from the Redis cache.

---

## ✅ What I Built

- Created an **EC2 instance** (Amazon Linux 2)
- Installed required packages: `pip`, `redis` (Python library)
- Connected to a **Redis cluster** on port `6379`
- Wrote and executed a **Python script** to:
  - Set a key-value pair in Redis
  - Retrieve and print the cached value

---

## 🧪 Setup & Commands

### 🔧 Install Tools on EC2

```bash
# Install pip
curl -O https://bootstrap.pypa.io/get-pip.py
python3 get-pip.py --user

# Install Redis client for Python
pip install redis
```

### 🐍 Python Script
[add-retrieve-value.md](add-retrieve-value.md)

## 📌 Key Learnings
How to connect EC2 to Amazon ElastiCache (Redis) over port 6379

Redis is an in-memory key-value store useful for low-latency caching

Simple Python clients can be used to set and retrieve cache values

Importance of VPC connectivity and security group rules for access

## 📁 Files Included
[add-retrieve-value.md](add-retrieve-value.md) – command guide with python script

[Screenshots](Screenshots/) – (optional) terminal logs and Redis test output

## 🔗 Related Links
[Main Hands-On Repo (aws-hands-on-lab-SAA)](https://github.com/MilosFaktor/aws-hands-on-lab-SAA)

## 🏷️ Tags
#AWS #ElastiCache #Redis #EC2 #HandsOnCloud #AWSProjects #Python #Caching #Port6379