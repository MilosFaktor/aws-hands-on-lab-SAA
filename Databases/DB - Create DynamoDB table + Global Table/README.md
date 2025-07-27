# 🚀 Hands-On AWS Project – DynamoDB in Action

As part of my AWS Solutions Architect Associate course in April, I built a fully functional DynamoDB workflow from using the AWS CLI:

✅ Created a DynamoDB table  
✅ Populated it via `batch-write-item` with JSON data in CloudShell  
✅ Queried and scanned the data directly from the CLI  
✅ Extended the setup by replicating it as a **Global Table** across regions for high availability 🌍

---

## 🧪 Sample CLI Commands I Used

### 📥 Upload JSON data
```bash
aws dynamodb batch-write-item --request-items file://estore-items.json
```
### 🔍 Scan the table
```bash
aws dynamodb scan --table-name estore
```
### 🔎 Query with Key Conditions
```bash
aws dynamodb query --table-name estore --key-conditions '{
  "clientid": {
    "ComparisonOperator": "EQ",
    "AttributeValueList": [ { "S": "harold@example.org" } ]
  }
}'
```
## 📌 What I Learned
This project helped me better understand:

DynamoDB data modeling

Global replication via Global Tables

Direct CLI interactions with DynamoDB

Real-world NoSQL design in AWS

## 📁 Files Included
estore-items.json – Sample data used for batch upload

screenshots/ – CLI and table result screenshots (optional)

## 🔗 Related Links
[Main Hands-On Repo (aws-hands-on-lab-SAA)](https://github.com/MilosFaktor/aws-hands-on-lab-SAA)

[Screenshots](Screenshots/)

## 🏷️ Tags
#AWS #DynamoDB #CloudShell #HandsOnCloud #SolutionArchitect #AWSCertified #NoSQL #GlobalTables #CloudProjects
