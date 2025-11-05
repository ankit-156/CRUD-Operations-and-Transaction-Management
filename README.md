# 🧠 Smart E-Learning Management System

### 🚀 Overview
The **Smart E-Learning Management System** is a Java-based web application designed to simplify online learning, course management, and student–teacher interaction.  
It provides a centralized platform for students, instructors, and administrators to manage all aspects of online education efficiently.

---

## 🎯 Objectives
- Provide a digital platform for interactive online learning.
- Enable students to register, enroll in courses, take quizzes, and view progress.
- Allow instructors to upload materials, manage students, and evaluate performance.
- Give admins full control over user, course, and system management.

---

## 🧩 Features

### 👩‍🎓 For Students
- Register and log in securely  
- Browse and enroll in courses  
- View and download study materials  
- Take online quizzes and track progress  

### 👨‍🏫 For Instructors
- Create and manage courses  
- Upload lectures, notes, and assignments  
- View enrolled students and grade submissions  

### 🧑‍💼 For Admins
- Manage users (students/instructors)  
- Add, update, or delete courses  
- Monitor system performance  

---

## ⚙️ Technologies Used
| Layer | Technology |
|-------|-------------|
| **Frontend** | HTML, CSS, JavaScript |
| **Backend** | Java, JSP, Servlets |
| **Database** | MySQL |
| **IDE** | NetBeans / VS Code |
| **Server** | Apache Tomcat |
| **Version Control** | Git & GitHub |

---

## 🧱 Project Structure

```
Smart-E-Learning/
│
├── src/
│   ├── com/
│   │   └── elearning/
│   │       ├── controller/
│   │       ├── dao/
│   │       ├── model/
│   │       └── util/
│
├── WebContent/
│   ├── WEB-INF/
│   │   └── web.xml
│   ├── pages/
│   │   ├── student/
│   │   ├── instructor/
│   │   └── admin/
│   ├── css/
│   ├── js/
│   └── images/
│
├── OUTPUT/
│   └── output_1.png
│
├── CombinedMainApp.java
└── README.md
```

---

## 🖼️ Output 

![Application Output](OUTPUT/output_1.png)

---

## 🧩 How to Run the Project

### 🪶 Prerequisites
- Install **Java JDK 17+**
- Install **Apache Tomcat 9+**
- Install **MySQL Server**
- IDE: **NetBeans / VS Code**

### 🪜 Steps to Run
1. Clone this repository  
   ```bash
   git clone https://github.com/yourusername/Smart-E-Learning-Management-System.git
   ```
2. Open the project in your preferred IDE.
3. Configure your **database connection** in `DBConnection.java`:
   ```java
   String url = "jdbc:mysql://localhost:3306/elearning_db";
   String username = "root";
   String password = "your_password";
   ```
4. Import the `elearning_db.sql` file into MySQL.
5. Build and run the project on **Apache Tomcat Server**.
6. Open your browser and go to:
   ```
   http://localhost:8080/Smart-E-Learning/
   ```

---

