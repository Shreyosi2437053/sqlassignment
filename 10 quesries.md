--QUESTION 1 -- INIT database -- Create the Students table CREATE TABLE Students ( student_id INT PRIMARY KEY, name VARCHAR(50), age INT, grade_level INT );

-- Create the Courses table CREATE TABLE Courses ( course_id INT PRIMARY KEY, course_name VARCHAR(50), credits INT );

-- Create the Enrollments table CREATE TABLE Enrollments ( enrollment_id INT PRIMARY KEY, student_id INT, course_id INT, grade DECIMAL(3, 2), FOREIGN KEY (student_id) REFERENCES Students(student_id), FOREIGN KEY (course_id) REFERENCES Courses(course_id) );

-- Insert sample data into Students INSERT INTO Students (student_id, name, age, grade_level) VALUES (1, 'Alice', 20, 3), (2, 'Bob', 21, 4), (3, 'Charlie', 19, 3), (4, 'Diana', 22, 4), (5, 'Ethan', 20, 3);

-- Insert sample data into Courses INSERT INTO Courses (course_id, course_name, credits) VALUES (1, 'Math', 3), (2, 'Science', 4), (3, 'History', 3), (4, 'Art', 2);

-- Insert sample data into Enrollments INSERT INTO Enrollments (enrollment_id, student_id, course_id, grade) VALUES (1, 1, 1, 3.5), (2, 1, 2, 4.0), (3, 2, 1, 2.5), (4, 2, 3, 3.0), (5, 3, 2, 3.0), (6, 3, 4, 2.0), (7, 4, 1, 3.5), (8, 4, 3, 4.0), (9, 5, 2, 3.0), (10, 5, 4, 3.5); SELECT AVG(grade) AS average_grade FROM Enrollment;

![image](https://github.com/user-attachments/assets/18c42390-af27-4e48-9464-c0823310e27a)

--QUESTION 2

SELECT Students.name, Courses.course_name FROM Students INNER JOIN Enrollments ON Students.student_id = Enrollments.student_id INNER JOIN Courses ON Enrollments.course_id = Courses.course_id; 1

![image](https://github.com/user-attachments/assets/6e6fe2d6-7fad-4958-b948-acc65a67cef2)

--QUESTION 3

SELECT grade_level, COUNT(*) AS student_count FROM Students GROUP BY grade_level;

![image](https://github.com/user-attachments/assets/9c8f787c-1440-449b-8199-790b630f21fc)

--QUESTION 4

SELECT Courses.course_name, MAX(Enrollments.grade) AS max_grade FROM Courses INNER JOIN Enrollments ON Courses.course_id = Enrollments.course_id GROUP BY Courses.course_name;

![image](https://github.com/user-attachments/assets/0e2a3b84-bbcb-4505-89e7-f9ccfbeb8501)

--QUESTION 5

SELECT AVG(grade) AS average_grade FROM Enrollments INNER JOIN Students ON Enrollments.student_id = Students.student_id WHERE Students.grade_level = 3;

![image](https://github.com/user-attachments/assets/6514f263-b485-461c-800b-f0420b5f664f)

--QUESTION 6

SELECT Students.name, Courses.course_name, Courses.credits FROM Students INNER JOIN Enrollments ON Students.student_id = Enrollments.student_id INNER JOIN Courses ON Enrollments.course_id = Courses.course_id;

![image](https://github.com/user-attachments/assets/185c4522-8ca9-4598-b935-267906c88bfc)

--QUESTION 7

SELECT Courses.course_name FROM Courses INNER JOIN Enrollments ON Courses.course_id = Enrollments.course_id GROUP BY Courses.course_id HAVING AVG(Enrollments.grade) > 3.0;

![image](https://github.com/user-attachments/assets/e6b44dce-9690-4e32-953b-d6c7e948e179)

--QUESTION 8

SELECT Students.student_id, Students.name FROM Students LEFT JOIN Enrollments ON Students.student_id = Enrollments.student_id WHERE Enrollments.grade IS NULL OR Enrollments.grade <> 4.0 GROUP BY Students.student_id, Students.name HAVING MAX(Enrollments.grade) IS NULL OR MAX(Enrollments.grade) <> 4.0;  

![image](https://github.com/user-attachments/assets/276be888-65b7-4532-b6fe-41fb8b8ab7ea)

--QUESTION 9

SELECT Students.name FROM Students INNER JOIN Enrollments ON Students.student_id = Enrollments.student_id GROUP BY Students.student_id HAVING AVG(Enrollments.grade) > (SELECT AVG(grade) FROM Enrollments);

![image](https://github.com/user-attachments/assets/abfe7e94-e995-4d75-a4eb-17199e0f8935)

--QUESTION 1O

SELECT Students.name, COUNT(Enrollments.course_id) AS total_courses, AVG(Enrollments.grade) AS average_grade FROM Students INNER JOIN Enrollments ON Students.student_id = Enrollments.student_id GROUP BY Students.student_id;

![image](https://github.com/user-attachments/assets/04ae3a13-6280-4701-93ed-16e1e22d3e58)








