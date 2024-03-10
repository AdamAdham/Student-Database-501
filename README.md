# Student-Database-501

**German University in Cairo**  

**Media Engineering and Technology  Dr. Mervat Abouelkheir**  

**Databases I,** Winter 2023** 

` `**Milestone 2                   *Submission: 01/12/2023 (11:59 pm)***

You are required to submit a zip file named after your **Team Number** containing the following documents: 

1) SQL file  
1) A PDF file containing:  
- Team name  
- Team leader name, ID and tutorial. 
- Team members’ names.  
- Team members’ IDs.  
- Team members’ tutorial groups. 
1. **Important Guidelines:** 
- All alpha-numeric attributes should be defined with type varchar (40).
- All numeric values should be defined with data type int or decimal.
- You must follow the names of the required functions, stored procedures and views. **Not matching the names will result in grade loss.**
- You must follow the order and data types of the parameters required for a stored procedure or function with a specific order and certain data type. Failing to follow this guideline will result in grade loss of that function/stored procedure/view.
- You must follow the order of the needed columns in case a table is required to be returned from a function or fetched from a view.
- You should do the appropriate join if you are required to implement a function/view that fetches data from different tables in your database.
- You should insert the data in the appropriate tables in your database if the required stored procedure inserts data in multiple tables in your database.
- Always think about all **consequences** and required actions to be done in every requirement.
- The status of any sent request can either be ‘pending’ (default), ‘accepted’ or ‘rejected’.
- The system needs to keep track of the selected courses’ grade per exam type and semester. 
- The type of any Exam can either be ‘Normal’ (default), ‘First\_makeup’ or 'Second\_makeup'.
- The grade will be ‘Null’ if the student is still taking the course or did not attend the Exam. If he/she took the course, a value should be assigned to the grade. 
- The status of the student (blocked or unblocked) should be represented using bit data type. if the student does not pay the installment by the deadline, the student will be blocked and unable to log in to the system.
- For students, 0 means blocked and 1 means unblocked.
- The status of any Payment can either be 'notPaid' (default), or 'Paid'.
- The Offered attribute of the course should be represented using bit data type
- For Course, ‘0’ means course is not offered in the current semester while ‘1’ means course is offered in the current semester.
- If the student has only one payment with no installments this means that number of installment attribute value should be ‘0’ not Null.
- If the student has any number of installments, please consider the below:
- Number of installments should be equals to the number of months between the payment’s start date and the payment’s deadline.
- The first installment’s start date equals to the payment start date.
- The start date of each upcoming installment is equals to the previous installment’s deadline.
- The deadline of each installment is a month from the installment’s start date.
- Installment’s amount is equal to (payment amount / total number of installments).
- Required courses: A course is considered required (according to a certain student) if it is unattended or failed.
- Failed course: Student failed in this course before and is not eligible for the 2nd makeup. 
- Unattended Course: A mandatory course from previous semesters that the student did not take before (Must be a course from a semester less than student’s current semester).
- Optional Courses: courses from the current semester or upcoming semesters (Student is allowed to take the optional course if he/she satisfied their prerequisites).
- Missing courses: The courses remaining to be taken at any semester in order for the student to graduate.
- **Any compilation/syntax error in any of the requirements will result in grade loss**
2. **Requirements:**  

   You are required to implement the following: 

1. **Basic Structure of the Database:** 
1. Write an SQL query to create database called “Advising\_Team\_Your Team Number”  
1. Put the queries that create all the tables of your database with their definition inside the below procedure.  
1. Type: stored procedure 
1. Name: CreateAllTables 
1. Input: Nothing 
1. Output: Nothing 
3. Create a procedure that Drop all tables inside your database. 
   1. Type: stored procedure 
   1. Name: DropAllTables 
   1. Input: Nothing 
   1. Output: Nothing 
3. Create a Stored procedure to clear all records in all tables existing in your database. 
1. Type: stored procedure 
1. Name: clearAllTables 
1. Input: Nothing 
1. Output: Nothing  
2. **Basic Data Retrieval** 
   1) Fetch details for all Active students.  
      1. Type: view 
      1. Name: view\_Students 
      1. Input: Nothing 
      1. Output: Student Table 
2) Fetch details for all courses with their prerequisites  
   1. Type: view 
   1. Name: view\_Course\_prerequisites 
   1. Input: Nothing 
   1. Output: Table 
2) Fetch details for all Instructors along with their assigned courses 
   1. Type: view 
   1. Name: Instructors\_AssignedCourses 
   1. Input: Nothing 
   1. Output: Table 
2) Fetch details for all payments along with their corresponding student 
1. Type: view 
1. Name: Student\_Payment 
1. Input: Nothing 
4. Output: Table 
5) Fetch details for all courses along with their corresponding slots’ details and instructors 
1. Type: view 
1. Name: Courses\_Slots\_Instructor 
1. Input: Nothing  
1. Output: Table (CourseID, Course.name, Slot ID, Slot Day, Slot Time, Slot Location, Slot’s Instructor name) 
6) Fetch details for all courses along with their exams’ details.  
1. Type: view 
1. Name: Courses\_MakeupExams 
1. Input: Nothing  
1. Output: Table (Course’s name, Course’s semester, MakeUp\_Exam details) 
7) Fetch students along with their taken courses’ details 
1. Type: view 
1. Name: Students\_Courses\_transcript 
1. Input: Nothing  
1. Output: table (Student id, student name, course id, course name, exam type, course grade, semester (the student took the course in), and Instructor’s name) 
8) Fetch all semesters along with their offered courses 
1. Type: view 
1. Name: Semster\_offered\_Courses 
1. Input: Nothing 
4. Output: Table (Course id, Course name, Semester code) 
9) Fetch all graduation plans along with their initiated advisors 
1. Type: view 
1. Name: Advisors\_Graduation\_Plan 
1. Input: Nothing 
1. Output: Table (Graduation\_Plan details, Advisor id, Advisor name) 
3. **All Other Requirements** 
1) Student Registration 
1. Type: Stored Procedure 
1. Name: Procedures\_StudentRegistration 
1. Input: first name varchar (40), last name varchar (40), password varchar (40), faculty varchar (40), email varchar (40), major varchar (40), Semester int. 
1. Output: Student id int 
2) Advisor Registration 
1. Type: Stored Procedure 
1. Name: Procedures\_AdvisorRegistration 
1. Input: advisor name varchar (40), password varchar (40), email varchar (40), office varchar (40), 
1. Output: Advisor id int 
3) List all advising students 
1. Type: Stored Procedure 
2. Name: Procedures\_AdminListStudents 
2. Input: Nothing 
2. Output: Table 
4) List all Advisors  
   1. Type: Stored Procedure 
   1. Name: Procedures\_AdminListAdvisors 
   1. Input: Nothing 
   1. Output: Table 
4) List all Students with their Advisors 
   1. Type: Stored Procedure 
   1. Name: AdminListStudentsWithAdvisors 
   1. Input: Nothing 
   1. Output: Table 
4) Add new Semester 
   1. Type: Stored Procedure 
   1. Name: AdminAddingSemester 
   1. Input: start\_date date, end\_date date, and semester code 
   1. Output: Nothing 
4) Add new course 
1. Type: Stored Procedure  
1. Name: Procedures\_AdminAddingCourse 
1. Input: major varchar (40), semester int, credit hours int, course name varchar (40), and offered bit 
4. Output: Nothing  
8) Link instructor to course on specific slot 
   1. Type: Stored Procedure 
   1. Name: Procedures\_AdminLinkInstructor 
   1. Input: InstructorId int, courseId int, and slotID int 
   1. Output: Nothing  
8) Link student to course with Specific instructor 
1. Type: Stored Procedure  
1. Name: Procedures\_AdminLinkStudent 
1. Input: Instructor Id int, student ID int, course ID, and semester code varchar (40)  
1. Output: Nothing 
10) Link student to advisor 
    1. Type: Stored Procedure 
    1. Name: Procedures\_AdminLinkStudentToAdvisor 
    1. Input: studentID int, advisorID int  
    1. Output: Nothing 
10) Admin add exam 
1. Type: Stored Procedure  
1. Name: Procedures\_AdminAddExam 
1. Input: Type varchar (40), date datetime, courseID int 
1. Output: Nothing 
12) Issue installments as per the number of installments for a certain payment 
    1. Type: Stored Procedure 
    1. Name: Procedures\_AdminIssueInstallment  
    1. Input: payment ID int 
    1. Output: Nothing 
12) Delete courses along with its related slots 
    1. Type: Stored Procedure 
    1. Name: Procedures\_AdminDeleteCourse 
    1. Input: courseID int 
    1. Output: Nothing 
12) Update student’s Status based on his/her financial status, if the students’ installment status was “NotPaid” and the installment’s deadline was passed then this student should be blocked. 

    (Student status should be 0 in case the student is blocked and 1 in case the student is Active). 

1. Type: Stored Procedure 
1. Name: Procedure\_AdminUpdateStudentStatus 
1. Input: StudentID int 
1. Output: Nothing 
15) List all pending requests 
1. Type: View 
1. Name: all\_Pending\_Requests 
1. Input: Nothing 
4. Output: Table (Pending requests details, initiated student name and Related advisor name) 
16) Delete slots of certain courses if the course isn’t offered in the current semester 
1. Type: Stored Procedure 
1. Name: Procedures\_AdminDeleteSlots 
1. Input: current\_semester varchar (40) 
1. Output: Nothing 
17) Advisor login using username and password. 
    1. Type: Scalar Function 
    1. Name: FN\_AdvisorLogin 
    1. Input: ID int, password varchar (40)  
    1. Output: Success bit 
17) Insert graduation Plan 
1. Type: Stored Procedure 
1. Name: Procedures\_AdvisorCreateGP 
1. Input: Semester code varchar (40), expected\_graduation\_date date, sem\_credit\_hours int, advisor id int, student id int 
1. Output: Nothing 
19) Add course inside certain plan of specific student 
1. Type: Stored Procedure 
1. Name: Procedures\_AdvisorAddCourseGP 

3. Input: student id int, Semester\_code varchar (40), course name varchar (40). 
3. Output: Nothing 
20) Update expected graduation date in a certain graduation plan 
    1. Type: Stored Procedure 
    1. Name: Procedures\_AdvisorUpdateGP 
    1. Input: expected\_grad\_date date and studentID int 
    1. Output: nothing 
20) Delete course from certain graduation plan in certain semester 
1. Type: stored procedure 
1. Name: Procedures\_AdvisorDeleteFromGP 
1. Input: studentID int, semester code varchar (40) and course ID (the course he/she wants to delete) 
1. Output: nothing 
22) Retrieve requests for certain advisor 
    1. Type: TVFunction 
    1. Name: FN\_Advisors\_Requests 
    1. Input: advisorID int 
    1. Output: Table (Requests details related to this advisor) 
22) Approve/Reject extra credit hours’ request 
1. Type: Stored Procedure 
1. Name: Procedures\_AdvisorApproveRejectCHRequest 
1. Input: RequestID int, Current semester code varchar (40) 

4. Output: nothing 
24) View all students assigned to specific advisor from a certain major along with their taken courses 
1. Type: Stored Procedure 
1. Name: Procedures\_AdvisorViewAssignedStudents 
1. Input: AdvisorID int and major varchar (40) 
1. Output: Table (Student id, Student name, Student major, Course name) 
25) Approve/Reject courses request  

    After approving/rejecting the request, the status of the request should be updated and all consequences should be handled. The approving/rejecting is based on the below conditions: 

- All the Requested course’s prerequisites are taken. 
- Student has enough assigned hours for the requested course. 
1. Type: Stored Procedure 
1. Name:Procedures\_AdvisorApproveRejectCourseRequest 
1. Input: RequestID int, current\_semester\_code varchar(40) 
1. Output: nothing 
26) View pending requests of specific advisor students 
1. Type: Stored Procedure 
1. Name: Procedures\_AdvisorViewPendingRequests 
1. Input: Advisor ID int {this advisor should be the one advising the student} 


4. Output: Table of pending requests’ details. 

AA)  Student Login using username and password. 

1. Type: Scalar Function 
1. Name: FN\_StudentLogin  
1. Input: Student ID int, password varchar (40)  
1. Output: Success bit 

BB)  Add Student mobile number(s) 

1. Type: Stored Procedure 
1. Name: Procedures\_StudentaddMobile  
1. Input: StudentID int, mobile\_number varchar (40) 
1. Output: Nothing 

CC)  View available courses in the current semester 

1. Type: TVFunction 
1. Name: FN\_SemsterAvailableCourses 
1. Input: semster\_code varchar (40) 
1. Output: Table of available courses within the semester 

DD)  Sending course’s request 

1. Type: Stored Procedure 
1. Name: Procedures\_StudentSendingCourseRequest 
1. Input:  Student ID int, course ID int, type varchar (40), and comment varchar (40)  

4. Output: Nothing 

EE)  Sending extra credit hours’ request 

1. Type: Stored Procedure 
1. Name: Procedures\_StudentSendingCHRequest 
1. Input:  Student ID int, credit hours int, type varchar (40), and comment varchar (40)  
1. Output: Nothing 

FF)  View graduation plan along with the assigned courses 

1. Type: TVFunction 
1. Name: FN\_StudentViewGP 
1. Input: student\_ID int 
1. Output:  Table (Student Id, Student\_name, graduation Plan Id, Course id, Course name, Semester code, expected graduation date, Semester credit hours, advisor id) 

GG)  Student view his first not paid installment deadline 

1. Type: Scalar Function 
1. Name: FN\_StudentUpcoming\_installment 
1. Input:  StudentID int 
1. Output: deadline date of first not paid installment 

HH)  View slots of certain course that is taught by a certain instructor 

1. Type: TVFunction 
1. Name: FN\_StudentViewSlot 
1. Input: CourseID int, InstructorID int 


4. Output: table of slots’ details (Slot ID, location, time, day) with course name and Instructor name 

II) Register for first makeup exam {refer to eligibility section (2.4.1) in Milestone 1} 

1. Type: Stored Procedure 
1. Name: Procedures\_StudentRegisterFirstMakeup 
1. Input: StudentID int, courseID int, studentCurrent semester varchar (40) 
1. Output: Nothing 

JJ) Second makeup Eligibility Check {refer to eligibility section (2.4.1) in the 

description} 

1. Type: Scalar Function 
1. Name: FN\_StudentCheckSMEligiability 
1. Input: CourseID int, Student ID int 
1. Output: Eligible bit {0 → not eligible, 1 → eligible} 

KK)  Register for 2nd makeup exam {refer to eligibility section (2.4.1) in the 

description} 

1. Type: Stored Procedure 
1. Name: Procedures\_StudentRegisterSecondMakeup 
1. Input: StudentID int, courseID int, Student Current Semester Varchar (40) 
1. Output: Nothing 

LL)  View required courses 

1. Type: Stored Procedure 
1. Name: Procedures\_ViewRequiredCourses 
3. Input: StudentID int, Current semester code Varchar (40) 
3. Output: Table of the required courses’ details. 

MM)  View optional courses 

1. Type: Stored Procedure 
1. Name: Procedures\_ViewOptionalCourse 
1. Input: StudentID int, Current semester code Varchar (40) 
1. Output: Table of the optional courses’ details. 

NN)  View missing/remaining courses to specific student. 

1. Type: Stored Procedure 
1. Name: Procedures\_ViewMS 
1. Input: StudentID int 
1. Output: Table of missing courses’ details 

OO)  Choose instructor for a certain selected course. 

1. Type: Stored Procedure 
1. Name: Procedures\_ChooseInstructor 
1. Input: Student ID int, Instructor ID int, Course ID int, current\_semester\_code varchar(40) 
1. Output: nothing 
