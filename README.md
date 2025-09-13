# 🔐 Encrypting Data with AWS KMS  

This project demonstrates how to use **AWS Key Management Service (KMS)** to secure data stored in **Amazon DynamoDB** by creating and managing Customer Managed Keys (CMKs), applying encryption, and validating access controls with IAM users.  

## 📌 Project Overview  
The goal of this project was to:  
- Create and manage an **encryption key** with AWS KMS.  
- Secure a **DynamoDB table** using the key.  
- Test access with different **IAM users** to validate encryption-based permissions.  
- Understand how **encryption adds a data-layer of security** compared to security groups and IAM policies.  

## 🛠️ Tools & Services Used  
- **AWS KMS (Key Management Service)** – for creating and managing encryption keys.  
- **Amazon DynamoDB** – NoSQL database used to store encrypted data.  
- **AWS IAM** – for configuring user permissions and testing access.  

## 📖 Steps Completed  
1. **Created a CMK (Customer Managed Key)** in AWS KMS and assigned admin ownership.  
2. **Provisioned a DynamoDB table** and enabled encryption using the CMK.  
3. **Added sample data** into the DynamoDB table.  
4. **Configured a test IAM user** with DynamoDB FULL access but without KMS decrypt permissions → verified access was **denied**.  
5. **Updated the KMS key policy** to grant decrypt permissions to the test user → verified access was **granted**.  
6. Compared **KMS encryption** vs traditional access controls, highlighting the **extra security layer at the data level**.  

## ✅ Key Learnings  
- Difference between **resource-level security (IAM, security groups)** and **data-level security (KMS encryption)**.  
- How **transparent data encryption** works in DynamoDB.  
- Using KMS key policies to **grant or restrict decryption rights** to IAM users.  
- Importance of **layered security**: IAM + Security Groups + KMS.  

## 🚀 How to Reproduce  
1. Create a **CMK** in AWS KMS.  
2. Deploy a **DynamoDB table** with CMK encryption enabled.  
3. Insert test data into the table.  
4. Create an **IAM user** with DynamoDB FULL access but without KMS permissions → confirm access is denied.  
5. Update the **KMS key policy** to include the IAM user → confirm access is restored.  

## 📂 Project Structure  
├── Encrypt Data with AWS KMS.pdf # Documentation of steps & learnings

└── README.md # Project overview

## 🔮 Future Improvements  
- Automate the process using **AWS CloudFormation or Terraform**.  
- Implement **asymmetric encryption** for scenarios requiring key-pair sharing.  
- Extend the project to secure **S3 objects** with KMS.  
