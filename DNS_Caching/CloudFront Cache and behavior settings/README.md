# 🚀 Hands-On AWS Project – CloudFront Cache and Behavior Settings

This project demonstrates how to configure **Amazon CloudFront** to route traffic to different **Amazon S3** origins based on file types using **CloudFormation**.

---

## ✅ What I Built

- Created **3 S3 buckets**:
  - One for the static website (`index.html`) – publicly accessible
  - One for storing **PDF files**
  - One for storing **JPG images**
- Created a **CloudFront distribution** with:
  - 3 origins (static website, PDF bucket, JPG bucket)
  - Custom **cache behavior settings**:
    - `*.pdf` → routed to the PDF bucket
    - `*.jpg` → routed to the JPG bucket
    - Default behavior → routes to the static website
- Disabled caching for all behaviors for simplicity of setting it up
- Ensured the static website is publicly accessible
- Used **Origin Access Control (OAC)** for securing non-public S3 buckets

---

## 🧪 Setup Steps

### 🪣 S3 Buckets

- `static-site-bucket`: public, static website hosting enabled
- `pdf-bucket`: private, contains `.pdf` files
- `jpg-bucket`: private, contains `.jpg` images

### 🌐 Static Website

- Uploaded `index.html` with links to test files
- Publicly accessible via S3 website endpoint

### 🌍 CloudFront Configuration

- Created distribution via CloudFormation
- Origins:
  - `Origin 1`: Static website bucket (uses S3 website endpoint)
  - `Origin 2`: PDF bucket (private, with OAC)
  - `Origin 3`: JPG bucket (private, with OAC)
- Behaviors:
  - `/\*.pdf` → PDF origin
  - `/\*.jpg` → JPG origin
  - Default → Static website origin
- CloudFront also provides a CDN layer for faster global content delivery, with optional caching and secured HTTPS access.

---

## 🎯 Behavior Logic

When a user opens `index.html`:
- Clicking a `.pdf` link → CloudFront routes to PDF S3 bucket
- Clicking a `.jpg` link → CloudFront routes to JPG S3 bucket

---

## 📁 Files Included

- `template.yaml` – CloudFormation template defining all resources
- `README.md` – Project documentation (this file)
- [Screenshots/](Screenshots/) – Folder with setup and output screenshots
- [src/](src/) – Static website source files:
  - [index.html](src/index.html) – Webpage with links to test files
  - [jpg/](src/jpg/) – Contains sample `.jpg` files
  - [pdf/](src/pdf/) – Contains sample `.pdf` files
  - [cloudfront-cache-and-behavior.md](src/cloudfront-cache-and-behavior.md) – Detailed CloudFront configuration guide


---

## 📌 Key Learnings

- How to configure **multiple S3 origins** in one CloudFront distribution
- Using **file extension-based cache behaviors** for routing
- Setting up **Origin Access Control (OAC)** for private S3 buckets
- Hosting and serving **hybrid content types** (PDFs, images, HTML) efficiently

---

## 🔗 Related Links

[Main Hands-On Repo (aws-hands-on-lab-SAA)](https://github.com/MilosFaktor/aws-hands-on-lab-SAA)

---

## 🏷️ Tags

#AWS #CloudFront #S3 #OAC #Caching #StaticWebsite #Serverless #HandsOnCloud #AWSProjects #CDN #CloudFormation
