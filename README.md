# Self Defence Academy Management System (SDAMS) 🥋

> **APU Level 2 Coursework - Object-Oriented Development with Java (OODJ)**  
> **Module Code:** CT038-3-2-OODJ  
> **Technology Stack:** Java (JDK 17+), Java Swing (GUI), Text File I/O  

---

## 📘 Project Overview

The **Self Defence Academy Management System (SDAMS)** is a desktop-based management application developed for the Self Defence Academy (SDA). The system digitizes daily operations across various martial arts disciplines (e.g., Karate, Judo, Taekwondo, MMA) by managing student registrations, class scheduling, attendance tracking, payment records, facility maintenance, and stock inventory.

Built strictly in accordance with **Object-Oriented Programming (OOP)** principles, the application utilizes **Java Swing** for its graphical user interface and **Text Files (`.txt`)** as the persistent data storage mechanism—without reliance on external database management systems.

---

## 👥 User Roles & Key Features

The system enforces strict Role-Based Access Control (RBAC), offering dedicated interfaces and workflows for **6 distinct user roles**:

### 1. 👔 Manager
- **Manage Administrators:** Full CRUD (Create, Read, Update, Delete) operations for Administrator accounts.
- **Staff Reports:** Filter staff records (Administrators, Instructors, Facilities Officers) by role and name, displaying aggregated totals.
- **Revenue Reports:** Generate monthly or yearly financial summaries detailing class registrations and total revenue.

### 2. 📋 Administrator
- **Manage Staff:** Comprehensive CRUD management for Instructors and Facilities Officers.
- **Manage Students:** Full CRUD management for student profiles.
- **Payment Records:** Search, view, and filter historical student payment entries.

### 3. 🥋 Instructor
- **Manage Schedule:** Create, update, view, and cancel martial arts training schedules and class availability.
- **Issue Facility Problems:** Report damaged mats, broken equipment, lighting/AC issues, or room damages.
- **View Ratings:** Track student feedback and average rating scores for completed classes.

### 4. 🥋 Student
- **Book Classes:** Search, book, reschedule, or cancel available training sessions.
- **Manage Payments:** Make online payments for registered classes and review past transaction histories.
- **Instructor Rating:** Submit ratings and feedback for instructors after attending classes.

### 5. 🛠️ Facilities Officer
- **Equipment Inventory Management:** Track and maintain inventory for martial arts gear (mats, punching bags, gloves, uniforms).
- **Facility Problem Management:** Review and resolve issues reported by instructors.
- **Inventory Stock Reports:** Filter and view equipment stock level summaries by ID or item name.

### 6. 📝 Attendance Officer
- **Manage Attendance:** Mark student attendance as *Present*, *Absent*, or *Late* post-class and rectify mistakes.
- **Attendance Records & Reports:** Search attendance histories and generate summaries by student, class, date, or martial arts discipline.

---

## 🔄 Core Workflows

1. **Class & Revenue Workflow:**  
   `Instructor` creates class ➔ `Student` books & pays ➔ `Attendance Officer` records attendance ➔ `Student` rates Instructor ➔ `Manager` reviews revenue analytics.
2. **Facility Maintenance Workflow:**  
   `Instructor` flags damaged facility/equipment ➔ `Facilities Officer` receives alert & updates progress ➔ Issue resolved & inventory updated.

---

## 🛠️ Object-Oriented System Architecture

The solution adheres to clean software architecture and core OOP paradigm principles:

- **Encapsulation:** Private domain attributes accessed via public getters/setters, paired with comprehensive input validation.
- **Inheritance:** Base class `User` extended by specialized user role classes (`Manager`, `Instructor`, `Student`, etc.).
- **Polymorphism:** Overridden methods for role-specific dashboard initialization, file parsing, and report generation.
- **Abstraction:** Modular service layers separating GUI logic from file handling and data parsing.
- **Data Persistence Layer:** Abstracted File I/O manager reading and writing structured text files using Delimiter-Separated Values (DSV).

---

## 📂 Data Storage Structure

Data is stored locally under the `data/` directory as plain text files:

```text
data/
├── users.txt           # Login credentials & role mapping
├── administrators.txt  # Admin user profiles
├── instructors.txt     # Instructor details & specialties
├── students.txt        # Student profiles & contact info
├── classes.txt         # Scheduled classes & capacity
├── bookings.txt        # Class registrations & status
├── payments.txt        # Payment logs & receipts
├── attendance.txt      # Class attendance logs
├── ratings.txt         # Student feedback & instructor scores
├── facilities.txt      # Reported facility problems
└── inventory.txt       # Equipment stock levels
