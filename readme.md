# EXPENSE TRACKER APPLICATION

## Project Documentation

### Submitted By

**Name:** Pallavi Dadi
**Project Title:** Expense Tracker Application

---

# 1. Introduction

The Expense Tracker Application is a full-stack web application developed to help users manage their daily expenses efficiently. The application allows users to add, view, update, delete, search, and sort expense records.

This project is built using:

* **Frontend:** Streamlit
* **Backend:** FastAPI
* **Database:** MySQL (Aiven Cloud Database)
* **Deployment Platforms:** Render (Backend), Streamlit Cloud (Frontend)

The application follows REST API architecture where the frontend communicates with the backend using HTTP requests.

---

# 2. Objectives

The main objectives of this project are:

* To track personal expenses digitally
* To perform CRUD operations on expense records
* To categorize expenses
* To search and sort expenses easily
* To deploy a full-stack cloud-based application

---

# 3. Technologies Used

| Technology       | Purpose                 |
| ---------------- | ----------------------- |
| Python           | Programming Language    |
| Streamlit        | Frontend Development    |
| FastAPI          | Backend API Development |
| MySQL            | Database                |
| Aiven            | Cloud Database Hosting  |
| Render           | Backend Deployment      |
| Streamlit Cloud  | Frontend Deployment     |
| Pandas           | Data Handling           |
| Requests Library | API Communication       |

---

# 4. System Architecture

## Architecture Flow

User → Streamlit Frontend → FastAPI Backend → MySQL Database (Aiven)

### Components Description

### Frontend (Streamlit)

The frontend provides a user-friendly interface where users can:

* Add expenses
* View expenses
* Update expenses
* Delete expenses
* Search expenses
* Sort expenses

### Backend (FastAPI)

The backend handles:

* API requests
* Database operations
* Data processing
* Communication with MySQL database

### Database (MySQL - Aiven)

The database stores:

* Expense ID
* Expense Title
* Amount
* Category
* Created Timestamp

---

# 5. Database Design

## Table Name: expenses

| Column Name | Data Type    | Description      |
| ----------- | ------------ | ---------------- |
| expense_id  | INT          | Primary Key      |
| title       | VARCHAR(100) | Expense Title    |
| amount      | INT          | Expense Amount   |
| category    | VARCHAR(100) | Expense Category |
| created_at  | TIMESTAMP    | Date and Time    |

## SQL Query

```sql
CREATE TABLE IF NOT EXISTS expenses(
    expense_id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(100),
    amount INT,
    category VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

# 6. Features of the Application

## 1. Add Expense

Users can add:

* Expense title
* Amount
* Category

### API Used

```python
POST /add_expense
```

---

## 2. View Expenses

Displays all expenses in tabular format.

### API Used

```python
GET /view_expenses
```

---

## 3. Delete Expense

Deletes an expense using Expense ID.

### API Used

```python
DELETE /delete_expense/{expense_id}
```

---

## 4. Update Expense

Updates existing expense details.

### API Used

```python
PUT /update_expense/{expense_id}
```

---

## 5. Search Expense

Searches expenses by category.

### API Used

```python
GET /search_expense/{category}
```

---

## 6. Sort Expenses

Sorts expenses based on amount.

### API Used

```python
GET /sort_expense/{sort_type}
```

---

# 7. Frontend Implementation

The frontend is developed using Streamlit.

## Main Functionalities

* Sidebar navigation
* Forms for user input
* Displaying data using DataFrames
* API integration using Requests library

## Libraries Used

```python
import streamlit as st
import requests as rq
import pandas as pd
```

---

# 8. Backend Implementation

The backend is developed using FastAPI.

## Main Functionalities

* REST API creation
* CRUD operations
* MySQL database connectivity
* CORS middleware handling

## Libraries Used

```python
from fastapi import FastAPI
from fastapi.middleware.cors import CORSMiddleware
import mysql.connector
import os
```

---

# 9. Deployment Details

## Frontend Deployment

* Platform: Streamlit Cloud
* Purpose: Hosting Streamlit frontend application

## Backend Deployment

* Platform: Render
* Purpose: Hosting FastAPI backend APIs

## Database Hosting

* Platform: Aiven
* Purpose: Cloud MySQL database hosting

---

# 10. API Endpoints

| Method | Endpoint                     | Description    |
| ------ | ---------------------------- | -------------- |
| GET    | /                            | Home Route     |
| POST   | /add_expense                 | Add Expense    |
| GET    | /view_expenses               | View Expenses  |
| DELETE | /delete_expense/{expense_id} | Delete Expense |
| PUT    | /update_expense/{expense_id} | Update Expense |
| GET    | /search_expense/{category}   | Search Expense |
| GET    | /sort_expense/{sort_type}    | Sort Expenses  |

---

# 11. Advantages of the Project

* Easy to use
* Cloud deployed application
* Real-time expense tracking
* Organized expense management
* Scalable architecture
* Beginner-friendly full-stack project

---

# 12. Challenges Faced

* Database connectivity during deployment
* API communication errors
* CORS issues
* Environment variable configuration
* Cloud deployment debugging

---

# 13. Future Enhancements

Future improvements can include:

* User authentication
* Monthly expense reports
* Data visualization charts
* Budget tracking
* Export to Excel/PDF
* Multi-user support
* Mobile responsive UI

---

# 14. Conclusion

The Expense Tracker Application successfully demonstrates full-stack web application development using modern technologies such as Streamlit, FastAPI, MySQL, Render, and Aiven. The application efficiently performs expense management operations and provides practical experience in frontend development, backend API creation, database management, and cloud deployment.

---

# 15. References

* Streamlit Documentation
* FastAPI Documentation
* MySQL Documentation
* Render Documentation
* Aiven Documentation
* Python Official Documentation

# 16. Steps to Run the Project

## Prerequisites

Before running the project, make sure the following are installed:

* Python 3.x
* MySQL Database
* VS Code or any IDE
* Git (Optional)

---

# 1. Clone the Project

```bash
git clone <your-github-repository-link>
```

Or download the ZIP file and extract it.

---

# 2. Open Project Folder

```bash
cd expense-tracker
```

---

# 3. Install Required Libraries

Install dependencies using pip.

## Backend Dependencies

```bash
pip install fastapi uvicorn mysql-connector-python python-dotenv
```

## Frontend Dependencies

```bash
pip install streamlit pandas requests
```

---

# 4. Create MySQL Database

Open MySQL and create a database.

```sql
CREATE DATABASE expense_tracker;
```

---

# 5. Configure Environment Variables

Create a `.env` file inside the backend folder.

## Example `.env`

```env
host=your_host
user=your_username
password=your_password
database=expense_tracker
port=3306
```

If using Aiven Cloud Database, use the credentials provided by Aiven.

---

# 6. Run Backend Server

Move to backend folder and run:

```bash
uvicorn main:app --reload
```

Backend will run on:

```bash
http://127.0.0.1:8000
```

---

# 7. Configure Frontend Secrets

Inside Streamlit project create:

```bash
.streamlit/secrets.toml
```

## Add:

```toml
server = "http://127.0.0.1:8000"
```

---

# 8. Run Streamlit Frontend

```bash
streamlit run app.py
```

Frontend will run on:

```bash
http://localhost:8501
```

---

# 9. Application Usage

After running both frontend and backend:

* Add expenses
* View expenses
* Update expenses
* Delete expenses
* Search expenses
* Sort expenses

---

# 10. Deployment Steps

## Backend Deployment (Render)

1. Push backend code to GitHub
2. Login to Render
3. Create New Web Service
4. Connect GitHub Repository
5. Add environment variables:

   * host
   * user
   * password
   * database
   * port
6. Start command:

```bash
uvicorn main:app --host 0.0.0.0 --port 10000
```

7. Deploy the service

---

## Frontend Deployment (Streamlit Cloud)

1. Push frontend code to GitHub
2. Login to Streamlit Cloud
3. Create New App
4. Select GitHub Repository
5. Add Streamlit Secrets:

```toml
server = "your-render-backend-url"
```

6. Deploy application

---

# 11. GitHub Repository Structure

```bash
expense-tracker/
│
├── backend/
│   ├── main.py
│   ├── requirements.txt
│   └── .env
│
├── frontend/
│   ├── app.py
│   └── .streamlit/
│       └── secrets.toml
│
└── README.md
```

---

# 12. Requirements File

## requirements.txt

```txt
fastapi
uvicorn
mysql-connector-python
python-dotenv
streamlit
pandas
requests
```
