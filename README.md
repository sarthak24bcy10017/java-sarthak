# College Course & Registration Management System (CCRM)

## Project Overview

The **College Course & Registration Management System (CCRM)** is a Java-based command-line application designed to manage students, courses, course enrollments, academic marks, grades, and student transcripts.

The application provides a simple menu-driven interface through which users can add and view student records, add and view courses, enroll students in courses, record marks, and generate a student transcript with GPA.

The project also demonstrates important Java concepts such as object-oriented programming, interfaces, inheritance, enums, collections, exception handling, the Builder Design Pattern, the Singleton Design Pattern, and file-system operations.

## Features

* Add and view student records.
* Store student registration number, name, email, and status.
* Activate and deactivate student status.
* Add and view courses.
* Store course code, title, credits, semester, and department.
* Enroll students into courses.
* Prevent duplicate course enrollment.
* Apply a maximum credit limit of **18 credits** per student.
* Record marks for enrolled courses.
* Automatically convert percentage marks into grades.
* Generate a student transcript.
* Calculate GPA based on course credits and grade points.
* Handle duplicate enrollment and maximum credit limit errors using custom exceptions.
* Store data temporarily using in-memory collections.
* Provide a file-system backup utility for creating backups of a specified directory.

## Technologies / Tools Used

* **Programming Language:** Java
* **Java Concepts:** OOP, Classes, Objects, Inheritance, Abstraction, Interfaces, Enums
* **Collections:** Map, Collection, ConcurrentHashMap
* **Exception Handling:** Custom Runtime Exceptions
* **Design Patterns:** Singleton Pattern and Builder Pattern
* **File Handling:** Java NIO (`java.nio.file`)
* **Date & Time:** Java Date/Time API
* **Development Environment:** Any Java-compatible IDE or terminal
* **Version Control:** Git and GitHub

## Project Structure

```text
CCRM-Project/
│
├── CCRMApp.java
├── README.md
└── statement.md
```

### Main Components

**AppConfig**

* Uses the Singleton pattern.
* Provides the application data folder.
* Generates timestamps for backup folders.

**Person**

* Abstract base class containing common details such as ID, name, email, and creation date.

**Student**

* Extends the Person class.
* Stores registration number and student status.
* Maintains the student's course enrollments.
* Generates a transcript and calculates GPA.

**Course**

* Stores course code, title, credits, semester, and department.
* Uses the Builder pattern for course creation.

**Enrollment**

* Connects a student with a course.
* Stores the grade obtained by the student.

**StudentService / CourseService**

* Provide operations for managing students and courses.

**EnrollmentService**

* Handles student enrollment.
* Checks duplicate enrollments.
* Checks the maximum credit limit.
* Records student marks.

**BackupService**

* Creates a timestamped backup directory and copies files using Java NIO.

## Installation & Setup

### Prerequisites

Make sure Java is installed on your computer.

Check Java installation using:

```bash
java -version
```

Check the Java compiler using:

```bash
javac -version
```

### Step 1: Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

### Step 2: Open the Project Folder

```bash
cd <YOUR_PROJECT_FOLDER>
```

### Step 3: Make Sure the Java File is Named Correctly

The Java source file should be:

```text
CCRMApp.java
```

This is required because the source code contains the public class:

```java
public class CCRMApp
```

### Step 4: Compile the Program

```bash
javac CCRMApp.java
```

### Step 5: Run the Application

```bash
java CCRMApp
```

## How to Use the Application

After starting the application, the main menu is displayed:

```text
1) Students 2) Courses 3) Enrollment 0) Exit
```

### 1. Students

Enter:

```text
1
```

The application displays existing students and asks whether you want to add a student.

For a new student, enter:

```text
RegNo:
Name:
Email:
```

### 2. Courses

Enter:

```text
2
```

The application displays existing courses and allows a new course to be added.

Enter:

```text
Code:
Title:
Credits:
```

### 3. Enrollment

Enter:

```text
3
```

Then provide:

```text
Student regNo:
Course code:
```

If the student and course exist, the student is enrolled.

The application also checks:

* Whether the student is already enrolled in the course.
* Whether adding the course exceeds the maximum limit of 18 credits.

The user can then choose whether to enter marks.

### 4. Record Marks and View Transcript

After enrollment, the application asks:

```text
Marks? (y/n):
```

If `y` is selected, enter the marks.

The system converts the percentage into a grade and displays the student's transcript and GPA.

## Grade System

| Percentage    | Grade | Grade Points |
| ------------- | ----- | -----------: |
| 90% and above | S     |           10 |
| 80%–89%       | A     |            9 |
| 70%–79%       | B     |            8 |
| 60%–69%       | C     |            7 |
| 50%–59%       | D     |            6 |
| 40%–49%       | E     |            5 |
| Below 40%     | F     |            0 |

## Testing Instructions

The following test cases can be used to verify the application.

### Test Case 1: Add Student

1. Start the application.
2. Select `1`.
3. Select `y`.
4. Enter registration number, name, and email.
5. Verify that the student is added.

### Test Case 2: Add Course

1. Select `2`.
2. Select `y`.
3. Enter course code, title, and credits.
4. Verify that the course appears in the course list.

### Test Case 3: Enroll Student

1. Select `3`.
2. Enter an existing student registration number.
3. Enter an existing course code.
4. Verify that `Enrolled.` is displayed.

### Test Case 4: Record Marks

1. After enrollment, select `y` for entering marks.
2. Enter a percentage.
3. Verify that the corresponding grade is displayed in the transcript.

### Test Case 5: GPA Calculation

1. Enroll a student in one or more courses.
2. Record marks.
3. View the transcript.
4. Verify that the GPA is calculated according to the course credits and grade points.

### Test Case 6: Duplicate Enrollment

Try enrolling the same student in the same course again.

Expected result:

```text
Already enrolled
```

### Test Case 7: Credit Limit

Enroll courses until adding another course would exceed the 18-credit limit.

Expected result:

```text
Exceeds limit
```

## Screenshots
![Uploading Screenshot 2026-09-17 210342.png…]()


1. Main menu
2. Adding a student
3. Adding a course
4. Successful enrollment
5. Marks entry
6. Student transcript and GPA
7. Duplicate enrollment error
8. Credit limit error

## Project Limitations

* Student and course data are stored in memory while the application is running.
* The current application uses a command-line interface rather than a graphical or web interface.
* Data is not automatically stored in a database.
* The backup utility is implemented as a reusable file-system utility and is separate from the main CLI menu.

## Conclusion

The CCRM project provides a basic college course and registration management system while demonstrating several core Java programming concepts. It manages students, courses, enrollments, marks, grades, and GPA through a simple command-line interface.

