

````markdown
# Student Records Database Management System

## 📌 Overview
This project is a **Relational Database Management System (RDBMS)** built using **MySQL**.  
It is designed to manage **student academic records** including departments, courses, lecturers, classrooms, enrollments, attendance, and exams.  

The database follows standard relational design principles with **well-structured tables, proper constraints, and relationships**.  

---

## 🎯 Features
- Database schema with **8 interrelated tables**.
- Supports **students, lecturers, courses, classrooms, and departments**.
- Includes **enrollment, attendance, and exams** tracking.
- Enforces **data integrity** with:
  - PRIMARY KEY
  - FOREIGN KEY
  - NOT NULL
  - UNIQUE
- Relationships implemented:
  - One-to-Many (Departments → Students, Lecturers → Courses)
  - Many-to-Many (Students ↔ Courses via Enrollments)
  - One-to-Many (Courses → Exams, Courses → Attendance)

---

## 🗂️ Database Structure
### Tables
1. **DEPARTMENTS** – Stores academic departments.
2. **LECTURERS** – Stores lecturer details, linked to departments.
3. **CLASSROOMS** – Stores classroom information with capacity.
4. **COURSES** – Stores courses, linked to departments, lecturers, and classrooms.
5. **STUDENTS** – Stores student details and department.
6. **ENROLLMENTS** – Junction table linking students and courses.
7. **ATTENDANCE** – Tracks student attendance per course.
8. **EXAMS** – Stores exam records for students in specific courses.

---

## ⚙️ Setup Instructions
1. Install **MySQL** on your system.
2. Clone this repository:
   ```bash
   git clone https://github.com/your-username/student-records-db.git
   cd student-records-db
````

3. Open MySQL client and run:

   ```sql
   SOURCE schema.sql;
   ```
4. This will:

   * Create the database `STUDENT_RECORDS`
   * Create all tables
   * Apply relationships and constraints

---

## 📑 Deliverables

* **CREATE DATABASE statement**
* **CREATE TABLE statements**
* **Relationship constraints** (PK, FK, UNIQUE, NOT NULL)

---

## 📊 Example Queries (You Can Try)

```sql
-- List all students with their department
SELECT S.StudentId, S.FirstName, S.LastName, D.DeptName
FROM STUDENTS S
JOIN DEPARTMENTS D ON S.DeptId = D.DeptId;

-- Show all courses with their lecturers
SELECT C.CourseCode, C.CourseTitle, L.FirstName, L.LastName
FROM COURSES C
JOIN LECTURERS L ON C.LecturerId = L.LecturerId;

-- List students enrolled in a specific course
SELECT S.FirstName, S.LastName, C.CourseTitle
FROM ENROLLMENTS E
JOIN STUDENTS S ON E.StudentId = S.StudentId
JOIN COURSES C ON E.CourseId = C.CourseId;

-- Get exam scores for each student in a course
SELECT S.FirstName, S.LastName, C.CourseTitle, E.Score
FROM EXAMS E
JOIN STUDENTS S ON E.StudentId = S.StudentId
JOIN COURSES C ON E.CourseId = C.CourseId;
```

---

## 📌 Notes

* No sample data is included in this repository file.
* You can add your own test records using `INSERT INTO` queries.
* The schema is flexible and can be extended to include more features like fees, library, or hostel management.

---

## 👨‍💻 Author

* **Your Name**
* GitHub: [your-username](https://github.com/your-username)

---

```

---

