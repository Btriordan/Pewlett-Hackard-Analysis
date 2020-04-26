# Pewlett-Hackard-Analysis
# Problem
  We were attempting to figure out how many people are retiring soon and what positions they are in.  This way the company can be prepared when those people do leave.  Also, they wanted us to look at who is elligible to be in the mentorship program to get new hires up to date.  
  
# Process
    We first figured out how many people are going to retire by looking at the ages of all the employees.  Looking at the employees.csv file, we were able to see who is retiring soon by looking at everyone that was born between 1/1/1952 through 12/31/1955.  I then merged the dept.emp and the new retirement page to figure out who is still working at the company.  We then merged the new table "current.emp", "titles" and "salaries" to determine which job each person who is near retirement is in.  Using the count and group by function, we were able to see how many retiring people were in each job.  
    In the next table we determined how many current employees are in the age range to be mentors.  We combined the employees and title files to see a list of eligable people and their titles.
    
# Results
The retiring counts are listed below:
  Engineer  -  2,711
  Senior Engineer  -  13,651
  Manager  -  2
  Assistant Engineer  - 251
  Staff  -  2,022
  Senior Staff  -  12,872
  Technique Leader  -  1,609
  
A limitation is we only lookd at the birth date for people to become eligible to be a mentor.  We should also look and see how long they have been with the company to make sure they are qualified.

ERD

Departments
-
dept_no varchar pk
dept_name varchar


Dept_emp
-
debt_no varchar pk fk - Departments.dept_no
emp_no varchar pk fk - Employees.emp_no
from_date date
to_date date

Titles
-
emp_no varchar pk fk - Employees.emp_no
title varchar
from_date
to_date

Salaries
-
emp_no varchar pk fk - Employees.emp_no
salary varchar
from_date date
to_date date

Employees
-
emp_no varchar pk fk - Employees.emp_no
birth_date date
first_name varchar
last_name varchar
gender carchar
hire_date date

Managers
-
debt_no varchar pk fk - Departments.dept_no
emp_no int fk - Employees.emp_no
from_date date 
to_date date
