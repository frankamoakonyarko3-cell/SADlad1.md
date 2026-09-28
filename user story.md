# Student GPA and Course Registration

## User Story

**As a student,**
I want to check my GPA and register for courses,
**so that** I can monitor my academic performance and complete my course registration for the semester.

---

## Feature: Student checks GPA and registers for courses

### Scenario 1: Student successfully logs into the student portal

**Given** the student is registered on the student portal
**And** the student has valid login credentials
**When** the student enters their username and password
**And** clicks the "Login" button
**Then** the student should be successfully logged in
**And** the student should see the student dashboard

---

### Scenario 2: Student checks their GPA

**Given** the student is logged into the student portal
**And** the student has completed courses with recorded grades
**When** the student selects "Academic Records"
**And** clicks "View GPA"
**Then** the system should display the student's current GPA
**And** the system should display the student's completed courses and grades

---

### Scenario 3: Student has no GPA available

**Given** the student is logged into the student portal
**And** the student has no completed courses or recorded grades
**When** the student selects "Academic Records"
**And** clicks "View GPA"
**Then** the system should display a message saying "GPA is not available"
**And** the system should explain that grades must be recorded before a GPA can be calculated

---

### Scenario 4: Student views available courses

**Given** the student is logged into the student portal
**And** the student is eligible to register for courses
**When** the student selects "Course Registration"
**Then** the system should display the courses available for the current semester
**And** the system should display the course code, course title, credit hours, and prerequisites

---

### Scenario 5: Student successfully registers for courses

**Given** the student is logged into the student portal
**And** the student is eligible to register for the selected courses
**And** the selected courses have no timetable conflicts
**When** the student selects the courses they want to register for
**And** clicks "Register Courses"
**Then** the system should register the selected courses
**And** the system should display a registration confirmation
**And** the registered courses should appear in the student's course list

---

### Scenario 6: Student attempts to register for a course without meeting the prerequisite

**Given** the student is logged into the student portal
**And** the student has not completed the prerequisite for a selected course
**When** the student attempts to register for that course
**Then** the system should prevent the registration
**And** the system should display a message explaining that the prerequisite has not been met

---

### Scenario 7: Student attempts to register for courses with a timetable conflict

**Given** the student is logged into the student portal
**And** the student has selected two courses scheduled at the same time
**When** the student clicks "Register Courses"
**Then** the system should prevent the conflicting courses from being registered
**And** the system should display a timetable conflict message
**And** the student should be allowed to modify their course selection

---

### Scenario 8: Student successfully completes GPA checking and course registration

**Given** the student is logged into the student portal
**And** the student's GPA is available
**And** courses are available for registration
**When** the student checks their GPA
**And** selects eligible courses
**And** submits the course registration
**Then** the system should display the student's GPA
**And** the system should register the selected courses
**And** the system should display a successful registration message
