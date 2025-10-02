title: "Proposal"
date: "2025-09-11"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The following content is for reference purposes only. Please **do not copy verbatim** into your final report, including this warning.
{{% /notice %}}

# Online Ebook Store Platform  
## A Java + AWS-Based Solution for Selling & Reading Digital Books  

### 1. Executive Summary  
The Online Ebook Store is designed for an IT student group (5 members) as part of their internship project. The platform enables users to **purchase and read digital books (ebooks, PDF/epub)** through an integrated reader (PDF.js). The solution introduces three user roles: **Admin (manage books & system), Staff (support & review moderation), and User (purchase & read books)**.  
The system leverages **AWS RDS, S3, CloudFront, Elastic Beanstalk, and IAM** to deliver a scalable, cost-effective, and secure deployment.  

### 2. Problem Statement  
*Current Issues*  
Free ebook libraries such as **nhasachmienphi.com** only allow users to read or download but lack user management, role-based access, order tracking, and revenue reporting features. Additionally, many existing online book platforms are overly complex or expensive to operate.  

*Proposed Solution*  
The ebook store system will:  
- Store and distribute digital books through **AWS S3 + CloudFront (signed URL)**.  
- Manage users, books, orders, and reviews on **AWS RDS (MySQL)**.  
- Deploy the Java Spring Boot backend with **Elastic Beanstalk**, and the frontend with **S3/CloudFront**.  
- Enforce role-based access control (Admin, Staff, User).  
- Integrate security with **IAM roles** and **JWT Authentication**.  

*Benefits & ROI*  
- A complete demo system that can be showcased as a potential commercial product.  
- Lower operating costs thanks to AWS Free Tier.  
- Easy scalability (from dozens to thousands of users).  
- Academic ROI: the team gains real-world experience in **full-stack development + cloud deployment**.  

### 3. Solution Architecture  
The platform follows a **3-tier architecture enhanced with AWS services**:  
- **Frontend**: ReactJS or Thymeleaf, displaying UI + PDF Viewer.  
- **Backend**: Spring Boot REST API (Auth, Books, Orders, Reviews).  
- **Database**: RDS MySQL.  
- **Storage**: S3 (covers & book files), CloudFront (signed URL distribution).  
- **Deployment**: Elastic Beanstalk (Java).  

*AWS Services Used*  
- **AWS RDS**: Store user, book, order, and review data.  
- **AWS S3**: Store ebook files & cover images.  
- **AWS CloudFront**: CDN + signed URLs for secure access.  
- **AWS Elastic Beanstalk**: Deploy the Spring Boot backend.  
- **AWS IAM**: Manage service permissions.  

### 4. Technical Implementation  
*Implementation Phases*  
1. **Design & local development**: NetBeans + local MySQL (1–2 weeks).  
2. **API & Frontend development**: CRUD for books, authentication, orders, reviews (2–3 weeks).  
3. **Testing & integration**: Role-based testing, purchase → read → review flow (1 week).  
4. **AWS deployment**: RDS, S3, CloudFront, Elastic Beanstalk (1–2 weeks).  

*Technical Requirements*  
- Java 17 + Spring Boot.  
- MySQL (local → RDS migration).  
- ReactJS or Thymeleaf + PDF.js.  
- AWS SDK for Java (integrating with S3).  
- Postman for API testing.  

### 5. Roadmap & Milestones  
- **Month 1**: Environment setup, build local DB.  
- **Month 2**: Develop backend API + basic UI.  
- **Month 3**: Integrate with AWS + testing + demo.  

### 6. Budget Estimation  
Based on AWS Pricing Calculator (Free Tier + $100 AWS credit):  
- **RDS MySQL**: 0.00 USD/month (750h Free Tier).  
- **S3**: 0.10–0.20 USD/month (5–10GB ebooks).  
- **CloudFront**: 0.05 USD/month (1GB traffic).  
- **Elastic Beanstalk**: 0.00 USD/month (EC2 Free Tier).  
- **IAM + CloudWatch**: free.  

*Total*: ~0.3 USD/month (effectively 0 due to Free Tier + credits).  

### 7. Risk Assessment  
- **AWS connection loss** → impacts demo (low risk).  
- **PDF file leakage** → mitigated with signed URLs.  
- **Exceeding Free Tier limits** → higher costs, requires AWS Billing Alarm monitoring.  

*Fallback Plan*  
- Maintain a local version (NetBeans + MySQL) for offline demo.  
- Enable AWS Billing Alarms to monitor costs.  

### 8. Expected Outcomes  
- **Technical**: A complete online ebook store full-stack system.  
- **Academic**: The team masters Spring Boot + ReactJS + AWS fundamentals.  
- **Practical**: The model can be extended into a real commercial platform.  
