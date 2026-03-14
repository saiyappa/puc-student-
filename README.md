# puc-student-
puc student 
# PUC Student Registration System (MERN Stack)

## Project Description

This project is a **PUC Student Registration System** built using the **MERN Stack**.

Students can:

* Register their details
* Login to the system
* View their dashboard

Admin can:

* View all student registrations
* Manage student data

Technologies Used:

* MongoDB
* Express.js
* React.js
* Node.js
* HTML, CSS, JavaScript

---

# Project Folder Structure

puc-registration/
│
├── client/        → React Frontend
├── server/        → Node + Express Backend
└── README.md

---

# Step 1: Install Required Software

Install the following:

1. Node.js
   https://nodejs.org

2. MongoDB Community Server
   https://www.mongodb.com/try/download/community

3. VS Code
   https://code.visualstudio.com/

---

# Step 2: Create Project Folder

Create a new folder:

puc-registration

Open it in VS Code.

---

# Step 3: Create Backend (Server)

Inside the project folder create:

server/

Open terminal and run:

cd server
npm init -y

Install packages:

npm install express mongoose cors

---

# Step 4: Create server.js

Create file:

server/server.js

Add code:

const express = require("express");
const mongoose = require("mongoose");
const cors = require("cors");

const app = express();

app.use(cors());
app.use(express.json());

mongoose.connect("mongodb://127.0.0.1:27017/pucDB")
.then(()=>console.log("MongoDB Connected"));

const Student = mongoose.model("Student",{
name:String,
email:String,
mobile:String,
city:String
});

app.post("/register", async(req,res)=>{
const student = new Student(req.body);
await student.save();
res.send("Student Registered");
});

app.listen(5000,()=>{
console.log("Server running on port 5000");
});

---

# Step 5: Run Backend Server

Open terminal inside server folder:

node server.js

Server will start:

Server running on port 5000

---

# Step 6: Create React Frontend

Open terminal in main project folder:

npx create-react-app client

Move into client folder:

cd client

Start React:

npm start

React will run on:

http://localhost:3000

---

# Step 7: Create Registration Form

Create new file:

client/src/Register.js

Add basic form to collect:

* Name
* Email
* Mobile
* City

Send data to backend API using fetch().

---

# Step 8: Connect Frontend with Backend

Use this API:

http://localhost:5000/register

Send POST request from React.

---

# Step 9: MongoDB Database

Database Name:
pucDB

Collection Name:
students

MongoDB stores student details like:

{
name: "Saiyappa",
email: "[sai@gmail.com](mailto:sai@gmail.com)",
mobile: "9876543210",
city: "Vijayapura"
}

---

# Step 10: Future Improvements

You can add:

* Student Login System
* Student Dashboard
* Admin Panel
* Search Student
* Edit / Delete Student
* Upload Photo
* Application Status System

---

# Author

Name: Saiyappa Lokhande
College: BLDE'A CET
Course: Computer Science
