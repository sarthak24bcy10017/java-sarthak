# Project Statement

## Problem Statement

Colleges need to maintain information about students, courses, enrollments, academic marks, grades, and student performance. Managing these activities manually can make it difficult to organize records and enforce enrollment rules.

The College Course & Registration Management System (CCRM) is developed as a Java-based command-line application to provide a simple way to manage student and course information, handle course enrollment, record marks, and generate student transcripts with GPA.

## Scope of the Project

The scope of the CCRM project includes:

* Managing student records.
* Managing course records.
* Enrolling students in courses.
* Preventing duplicate course enrollment.
* Applying a maximum credit limit of 18 credits.
* Recording marks for enrolled courses.
* Converting percentage marks into grades.
* Generating student transcripts.
* Calculating GPA using course credits and grade points.
* Demonstrating file-system backup functionality.
* Demonstrating object-oriented programming and Java design patterns.

The current project is a command-line application and uses in-memory storage for student and course information.

## Target Users

The intended users of the system are:

* **College/University Administrators** – for maintaining student and course information.
* **Academic Staff** – for managing course enrollment and recording academic marks.
* **Students** – for viewing their enrollment information and academic transcript.
* **Developers/Students** – for learning and demonstrating Java, OOP, collections, exception handling, and design patterns.

## High-Level Features

### 1. Student Management

The system allows users to add and view student records. Each student contains information such as registration number, name, email, and status.

### 2. Course Management

Users can add and view courses. Each course can contain a course code, title, credit value, semester, and department.

### 3. Course Enrollment

Students can be enrolled in available courses. The system prevents a student from enrolling in the same course more than once.

### 4. Credit Limit Validation

The system applies a maximum credit limit of 18 credits. An enrollment is rejected if adding the course would exceed this limit.

### 5. Marks and Grade Management

Marks can be recorded for enrolled courses. The system converts percentage marks into grades ranging from S to F according to the defined grading scale.

### 6. Transcript and GPA

The system generates a transcript showing enrolled courses and grades. It also calculates GPA using grade points and course credits.

### 7. Exception Handling

Custom exceptions are used to handle invalid enrollment situations, including duplicate enrollment and exceeding the maximum credit limit.

### 8. Backup Utility

The project contains a backup utility that creates a timestamped backup folder and copies files from a specified source directory using Java file-system operations.

### 9. Object-Oriented Design

The project demonstrates abstraction, inheritance, interfaces, encapsulation, enums, collections, and reusable service classes.

### 10. Design Patterns

The project demonstrates the **Singleton pattern** through `AppConfig` and the **Builder pattern** through the `Course.Builder` class.
