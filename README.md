# 📊 Research Projects Database

This project implements a relational database schema to manage information about **research projects**, their **managers**, **employees**, and **funding agencies** using SQL.

---

## 🧾 Project Description

The database is designed to capture real-world scenarios involving research projects funded by various agencies and managed by employees within an organization. It supports the following key features:

- Track **employees** (SSN, name, salary).
- Maintain **projects** (name, duration, budget, and managing employee).
- Record **funding agencies** with address details.
- Associate projects with a single funding agency.
- Allow employees to work on multiple projects.
- Managers are also employees who manage specific projects.
- Maintain relationships between employees, projects, and their respective managers.

---

## 🗂️ Database Tables

### 1. `Employee`
Stores employee details.

| Column   | Type         | Description         |
|----------|--------------|---------------------|
| SSN      | INT (PK)     | Employee ID         |
| Emp_Name | VARCHAR(50)  | Employee Name       |
| Salary   | DECIMAL      | Employee Salary     |

---

### 2. `FundingAgency`
Details of funding agencies.

| Column   | Type         | Description         |
|----------|--------------|---------------------|
| Agency_ID | INT (PK)    | Unique Agency ID    |
| Name     | VARCHAR(100) | Agency Name         |
| Address  | VARCHAR(255) | Agency Address      |

---

### 3. `Project`
Contains project-specific information.

| Column    | Type           | Description           |
|-----------|----------------|-----------------------|
| Project_ID | INT (PK)      | Unique Project ID     |
| Name      | VARCHAR(100)   | Project Name          |
| Duration  | INT            | Duration in months    |
| Budget    | DECIMAL(12,2)  | Project Budget        |

---

### 4. `Project_Manager`
Represents the manager of each project (one-to-one).

| Column       | Type     | Description          |
|--------------|----------|----------------------|
| Project_ID   | INT (PK) | Managed Project ID   |
| Manager_SSN  | INT      | Manager's SSN (FK)   |

---

### 5. `Employee_Project`
Many-to-many relationship between employees and projects. Tracks both workers and their respective project managers.

| Column       | Type     | Description            |
|--------------|----------|------------------------|
| SSN          | INT      | Employee SSN (FK)      |
| Project_ID   | INT      | Project ID (FK)        |
| Manager_SSN  | INT      | Manager SSN (FK)       |

---

## 🔢 Sample Data

Sample records are provided for:

- Employees: John, Jane, and Alice
- Projects: AI Research, Cloud Migration, Blockchain Platform
- Agencies: Tech Research Fund, Innovation Grants Inc., Global Funding Group
- Managers assigned per project
- Employee-to-project work mappings

---

## 💻 Technologies Used

- **MySQL**
- **SQL DDL & DML**
- ER-model-based design

---

## 📂 How to Use

1. Clone the repository.
2. Run the SQL scripts in your MySQL environment.
3. Extend with more queries or front-end/reporting tools as needed.

---

## 📌 Notes

- Project names are assumed to be unique **within each agency**.
- Managers are regular employees who can also work on other projects.
- Each project has only one funding agency.

---

## 🧑‍💻 Author

Developed as part of a Database Management System (DBMS) academic project.

