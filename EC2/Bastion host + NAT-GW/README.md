# 🛡️ NAT Gateway Setup – Private Instance Internet Access

This hands-on lab demonstrates how to enable outbound internet access for an EC2 instance in a private subnet using a **NAT Gateway**.

---

## ✅ Key Concepts

- **NAT Gateway** must be placed in a **public subnet**.
- **Private subnet's route table** must route `0.0.0.0/0` through the **NAT Gateway**.
- A **bastion host** in the public subnet is used to SSH into the private instance.
- Once the NAT Gateway is configured, the **private instance can access the internet**.

---

## 🔧 Setup Steps

1. ✅ **Launch Two EC2 Instances**:
   - `public-instance` in a **public subnet**.
   - `private-instance` in a **private subnet**.

2. ✅ **Create a NAT Gateway**:
   - Attach it to a public subnet.
   - Associate an **Elastic IP**.

3. ✅ **Update Route Table of Private Subnet**:
   - Add a route:
     - `Destination`: `0.0.0.0/0`
     - `Target`: Your NAT Gateway ID

4. ✅ **Connect to Private Instance via Bastion Host**:
   - On the bastion host (public EC2 instance), create a PEM file:
     ```bash
     nano Gaming_key.pem
     chmod 600 Gaming_key.pem
     ssh -i Gaming_key.pem ec2-user@172.31.60.129
     ```

5. ✅ **Test Internet Connectivity from Private Instance**:
   - Run `ping google.com`
   - Internet access is routed through the NAT Gateway.

---

## 🖼️ Screenshots

- [EC2 Instances – Public and Private](Screenshots/1%20-%20bastion%20host(public)%20and%20private%20EC2%20instances.png)
- [NAT Gateway Configuration](Screenshots/2%20-%20NAT-GW.png)
- [Route Table for Private Subnet](Screenshots/3%20-%20route%20tables%20for%20private%20instance.png)
- [Internet Access from Private Instance](Screenshots/4%20-%20private%20instance%20through%20NAT%20GateWay.png)

---

## 🧠 Key Learning

> Private subnets **do not have internet access by default**.  
> **NAT Gateway** allows outbound connections while keeping instances unreachable from the outside.

---

#AWS #NATGateway #VPC #PrivateSubnet #EC2 #RouteTables #Networking #CloudNetworking #HandsOnCloud #AWSProjects #SolutionArchitect #AWSCertified #BastionHost #Infrastructure
