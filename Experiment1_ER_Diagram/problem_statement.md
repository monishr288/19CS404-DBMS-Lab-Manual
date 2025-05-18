# Experiment 1: Entity-Relationship (ER) Diagram
```
Name: MONISH R
Reg No: 212223220061
```
## Scenario Chosen:
University

## ER Diagram:

![Screenshot 2025-05-18 201957](https://github.com/user-attachments/assets/6ff5573b-275a-4a5c-9bb4-df6235534468)


## Entities and Attributes:
### Student:
Attributes: StudentID (PK), Name, Gender, DOB, Email, Phone, Address
### Instructor:
Attributes: InstructorID (PK), Name, Phone, Email
### Department:
Attributes: DepartmentID (PK), Department Name, Head of Department (FK → Instructor.InstructorID)
### Course:
Attributes: CourseID (PK), Course Name, Credits, DepartmentID (FK → Department.DepartmentID)
### Enrollment:
Attributes: EnrollmentID (PK), EnrollmentDate, Grade, StudentID (FK → Student.StudentID), CourseID (FK → Course.CourseID)
### Schedule:
Attributes: ScheduleID (PK), Day, Time, CourseID (FK → Course.CourseID), InstructorID (FK → Instructor.InstructorID), ClassroomID (FK → Classroom.ClassroomID)
### Classroom:
Attributes: ClassroomID (PK), Building, Room Number, Capacity

## Relationships and Constraints:
### Enrollment (EnrollmentID, StudentID, CourseID)
PK: EnrollmentID
FKs:
StudentID → Student(StudentID)
CourseID → Course(CourseID)
Type: Many-to-Many (via associative entity)
### Course (CourseID, DepartmentID)
PK: CourseID
FK: DepartmentID → Department(DepartmentID)
Type: Many-to-One
### Instructor (InstructorID, CourseID) (via Schedule or a separate junction table)
PK: InstructorID
Relationship Type: Many-to-Many
### Schedule (ScheduleID, CourseID, ClassroomID, InstructorID)
PK: ScheduleID
FKs:
CourseID → Course(CourseID)
InstructorID → Instructor(InstructorID)
ClassroomID → Classroom(ClassroomID)
Type: Composite Association

## Extension – Prerequisite Modeling:
Prerequisites can be added by introducing a recursive relationship on the Course entity:
"PrerequisiteFor"
CourseID → PrerequisiteCourseID
Useful attributes: Type of prerequisite (compulsory/elective)

## Design Choices Explanation:
The model clearly separates core academic entities such as Student, Instructor, Course, Department, and Classroom.
Use of Enrollment and Schedule as associative entities ensures normalization and supports M:N relationships effectively.
The use of attributes like EnrollDate, Grade, and ScheduleID within relationships shows a thoughtful mapping of transactional aspects.
The design is modular, scalable, and easily supports queries related to student progress, scheduling, and faculty management.

## RESULT:
Thus, we have created an E-R Diagram for the chosen scenario successfully, defining the necessary entities, attributes, relationships, and constraints.
