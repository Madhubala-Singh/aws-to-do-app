AWS Serverless To-Do Application

A fully serverless, scalable, and modern To-Do application built using AWS cloud services.
This project demonstrates a complete CRUD application with a sleek frontend and a fully managed backend.

🌟 Features
✔ Add new tasks
✔ Fetch all tasks
✔ Delete tasks
✔ No servers to manage
✔ Modern and clean UI
✔ Fast, secure, and low-cost
✔ Perfect for learning AWS and showcasing in your resume

🧰 Technology Stack
Frontend
HTML5
CSS3
JavaScript (Fetch API)
Styled Modern UI
Backend (Serverless)
AWS Lambda (Node.js)
addTask
getTasks
deleteTask
AWS API Gateway (REST API)
POST /add
GET /tasks
DELETE /delete
Database
Amazon DynamoDB (NoSQL)
Table: Tasks
Partition Key: taskId

Hosting:
Amazon S3 Static Website Hosting
- Amazon S3 (Static website hosting)

Project Structure:
aws-to-do-app/
│
├── index.html
├── index_modern.html        # Polished modern UI version
├── README.md                # Documentation
│
└── backend/                 # Lambda functions
      addTask.js
      getTasks.js
      deleteTask.js

Architecture:-

Browser (HTML/JS)
        ↓
Amazon S3 (Static Hosting)
        ↓
API Gateway (REST Endpoints)
        ↓
AWS Lambda (Business Logic)
        ↓
DynamoDB (Database)
This architecture is fully serverless — AWS automatically scales everything.


⚙️ Setup Instructions (High-Level)
1️⃣ Create DynamoDB Table

Name: Tasks
Partition Key: taskId (String)

2️⃣ Create IAM Role (lambda-dynamodb-role)

Attach:
AmazonDynamoDBFullAccess
CloudWatchFullAccess
Assign this role to all Lambda functions.

3️⃣ Create 3 Lambda Functions

addTask
getTasks
deleteTask
Runtime: Node.js 24.x
Paste your Lambda code into each function.

4️⃣ Create REST API in API Gateway

Endpoints:
Method	Path	Connected Lambda
POST	/add	addTask
GET	/tasks	getTasks
DELETE	/delete	deleteTask
Enable CORS → Deploy API → Stage name: prod
Copy your Invoke URL, e.g.:
https://abcd1234.execute-api.eu-north-1.amazonaws.com/prod

5️⃣ Update Frontend

In your index.html or index_modern.html:
const API_BASE = "YOUR_API_URL_HERE";

6️⃣ Host Frontend on Amazon S3:
Upload HTML files
Make public-
Enable Static Website Hosting

Open website via S3 URL:
http://your-bucket-name.s3-website-region.amazonaws.com

🧪 Testing:-
Add tasks — should appear instantly
Refresh page → tasks load from DynamoDB
Delete tasks → removed immediately

🎯 Why This Project Is Great for Your Resume?

Shows real AWS experience
Uses 4+ AWS services together
Demonstrates backend + frontend skills
Proves knowledge of serverless architecture
Great talking point in interviews.


      


