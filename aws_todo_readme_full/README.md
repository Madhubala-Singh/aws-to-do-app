# AWS Serverless To-Do Application

A fully serverless To-Do application built using AWS Lambda, API Gateway, DynamoDB, and Amazon S3.
This project demonstrates how to create a complete CRUD application using AWS services with a modern UI.

## 🚀 Project Features
- Add new tasks  
- View all tasks  
- Delete tasks  
- Serverless backend (Lambda + API Gateway)  
- DynamoDB NoSQL database  
- Static hosting on Amazon S3  
- Modern HTML/CSS/JavaScript frontend  

## 📁 Project Structure
```
aws-to-do-app/
│
├── index.html
├── index_modern.html
├── README.md
│
└── backend/ 
      (Lambda functions not included here)
```

## 🏗 Architecture
```
Browser → S3 → API Gateway → Lambda → DynamoDB
```

## 🛠 Technologies Used
- Amazon S3  
- AWS Lambda  
- API Gateway  
- DynamoDB  
- JavaScript (Frontend)

---

# ☁️ AWS Setup Guide

## ✔ Step 1 — Create DynamoDB Table
1. Go to DynamoDB → Create table  
2. Table Name: `Tasks`  
3. Partition Key: `taskId` (String)  

---

## ✔ Step 2 — Create IAM Role
Name: `lambda-dynamodb-role`

Attach:
- AmazonDynamoDBFullAccess
- CloudWatchFullAccess

---

## ✔ Step 3 — Create Lambda Functions
Create 3 Lambda functions:
- addTask
- getTasks
- deleteTask

Runtime: Node.js 24.x  
Assign IAM role: lambda-dynamodb-role

(Backend code excluded in this README)

---

## ✔ Step 4 — Setup API Gateway (REST API)
Create resources:
- POST /add
- GET /tasks
- DELETE /delete

Enable CORS  
Deploy API → Stage: `prod`

Copy API URL:
```
https://xyz123.execute-api.region.amazonaws.com/prod
```

---

## ✔ Step 5 — Update Frontend
In `index.html`, set:
```
const API_BASE = "YOUR_API_URL_HERE";
```

---

## ✔ Step 6 — Host Frontend on S3
1. Create S3 bucket  
2. Disable Block Public Access  
3. Upload index.html  
4. Make public  
5. Enable Static Website Hosting  
6. Open the Website URL:
```
http://your-bucket-name.s3-website-region.amazonaws.com
```

---

# 🧪 Testing
- Add task  
- Get tasks  
- Delete task  

---

# 📤 Upload to GitHub (Beginner-Friendly)

1. Open your GitHub repo  
2. Click **Add file → Upload files**  
3. Drag & drop:
   - index.html
   - index_modern.html
   - README.md
   - backend folder (optional)
4. Click **Commit changes**

---

# 🎯 Conclusion
You now have a complete AWS serverless application with:
- Lambda backend
- API Gateway
- DynamoDB
- S3 static frontend

Perfect for resume, learning AWS, and real projects.
