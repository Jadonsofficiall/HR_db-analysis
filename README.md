# HR_db-analysis
Analysis on synthetic hr database.

# DDL and DQL
-- Creating the schema
CREATE SCHEMA `hr_db`;

-- Creating tables for the hr_db
USE `hr_db`;

CREATE TABLE biodata (
  emp_id          VARCHAR(10)  PRIMARY KEY,
  full_name       VARCHAR(100) NOT NULL,
  gender          CHAR(1)      NOT NULL,
  date_of_birth   DATE,
  state_of_origin VARCHAR(30),
  department      VARCHAR(30),
  date_hired      DATE
);

CREATE TABLE performance_details (
  perf_id        INT PRIMARY KEY,
  emp_id         VARCHAR(10) NOT NULL,
  review_year    INT,
  kpi_score      INT,
  rating         VARCHAR(20),
  training_hours INT,
  FOREIGN KEY (emp_id) REFERENCES biodata(emp_id)
);

CREATE TABLE payroll_details (
  pay_id       INT PRIMARY KEY,
  emp_id       VARCHAR(10) NOT NULL,
  pay_month    CHAR(7),
  basic_salary DECIMAL(12,2),
  allowances   DECIMAL(12,2),
  deductions   DECIMAL(12,2),
  net_pay      DECIMAL(12,2),
  FOREIGN KEY (emp_id) REFERENCES biodata(emp_id)
);

-- Profilling the tables
SELECT *
FROM biodata;

SELECT *
FROM performance_details;

SELECT *
FROM payroll_details;

## Inserting values into the tables
-- Inserting values into the biodata table
INSERT INTO biodata (emp_id, full_name, gender, date_of_birth, state_of_origin, department, date_hired)
VALUES
('EMP001', 'Adaeze Okafor', 'F', '1990-04-12', 'Anambra', 'Finance', '2015-03-01'),
('EMP002', 'Tunde Bakare', 'M', '1985-09-30', 'Oyo', 'Sales', '2012-07-16'),
('EMP003', 'Ngozi Eze', 'F', '1992-01-22', 'Enugu', 'HR', '2017-11-06'),
('EMP004', 'Ibrahim Musa', 'M', '1988-06-05', 'Kano', 'Operations', '2014-02-17'),
('EMP005', 'Chioma Nwosu', 'F', '1995-12-19', 'Imo', 'Marketing', '2019-05-27'),
('EMP006', 'Emeka Obi', 'M', '1983-03-14', 'Abia', 'IT', '2010-09-01'),
('EMP007', 'Halima Sani', 'F', '1994-08-08', 'Kaduna', 'Finance', '2018-01-15'),
('EMP008', 'Yusuf Abdullahi', 'M', '1991-11-02', 'Bauchi', 'Operations', '2016-06-20'),
('EMP009', 'Funke Adeyemi', 'F', '1989-05-25', 'Ogun', 'Sales', '2013-10-07'),
('EMP010', 'David Ifeanyi', 'M', '1997-02-10', 'Delta', 'IT', '2021-03-08'),
('EMP011', 'Blessing Akpan', 'F', '1993-07-03', 'Akwa Ibom', 'HR', '2016-08-29'),
('EMP012', 'Kelechi Amadi', 'M', '1986-10-17', 'Rivers', 'Operations', '2011-04-18'),
('EMP013', 'Aisha Bello', 'F', '1996-04-28', 'Niger', 'Marketing', '2020-07-13'),
('EMP014', 'Segun Ogunleye', 'M', '1980-12-01', 'Lagos', 'Finance', '2008-02-04'),
('EMP015', 'Ruth Danjuma', 'F', '1998-09-09', 'Taraba', 'Sales', '2022-01-10'),
('EMP016', 'Obinna Chukwu', 'M', '1990-01-30', 'Ebonyi', 'IT', '2015-10-19'),
('EMP017', 'Mercy Udoh', 'F', '1987-06-16', 'Akwa Ibom', 'Marketing', '2012-12-03'),
('EMP018', 'Musa Garba', 'M', '1984-02-21', 'Katsina', 'Operations', '2009-05-11'),
('EMP019', 'Ifeoma Okonkwo', 'F', '1999-03-27', 'Anambra', 'HR', '2023-02-06'),
('EMP020', 'Tobi Afolabi', 'M', '1993-10-05', 'Ekiti', 'Sales', '2019-09-16')
;

-- Inserting values into the performance_details table
INSERT INTO performance_details (perf_id, emp_id, review_year, kpi_score, rating, training_hours)
VALUES
(1, 'EMP001', 2025, 88, 'Exceeds', 24),
(2, 'EMP002', 2025, 72, 'Meets', 12),
(3, 'EMP003', 2025, 91, 'Exceeds', 30),
(4, 'EMP004', 2025, 58, 'Below', 6),
(5, 'EMP005', 2025, 80, 'Exceeds', 18),
(6, 'EMP006', 2025, 95, 'Outstanding', 36),
(7, 'EMP007', 2025, 67, 'Meets', 10),
(8, 'EMP008', 2025, 74, 'Meets', 16),
(9, 'EMP009', 2025, 83, 'Exceeds', 20),
(10, 'EMP010', 2025, 61, 'Below', 8),
(11, 'EMP011', 2025, 77, 'Meets', 14),
(12, 'EMP012', 2025, 69, 'Meets', 9),
(13, 'EMP013', 2025, 86, 'Exceeds', 22),
(14, 'EMP014', 2025, 92, 'Outstanding', 28),
(15, 'EMP015', 2025, 54, 'Below', 5),
(16, 'EMP016', 2025, 79, 'Meets', 15),
(17, 'EMP017', 2025, 88, 'Exceeds', 26),
(18, 'EMP018', 2025, 63, 'Meets', 7),
(19, 'EMP019', 2025, 70, 'Meets', 11),
(20, 'EMP020', 2025, 85, 'Exceeds', 21)
;

-- Inserting values into the payroll_details table
INSERT INTO payroll_details (pay_id, emp_id, pay_month, basic_salary, allowances, deductions, net_pay)
VALUES
(1, 'EMP001', '2026-09', 350000, 120000, 45000, 425000),
(2, 'EMP002', '2026-09', 280000, 90000, 36000, 334000),
(3, 'EMP003', '2026-09', 310000, 100000, 40000, 370000),
(4, 'EMP004', '2026-09', 200000, 60000, 25000, 235000),
(5, 'EMP005', '2026-09', 260000, 85000, 33000, 312000),
(6, 'EMP006', '2026-09', 420000, 150000, 55000, 515000),
(7, 'EMP007', '2026-09', 330000, 110000, 42000, 398000),
(8, 'EMP008', '2026-09', 190000, 55000, 22000, 223000),
(9, 'EMP009', '2026-09', 275000, 88000, 35000, 328000),
(10, 'EMP010', '2026-09', 300000, 95000, 38000, 357000),
(11, 'EMP011', '2026-09', 240000, 70000, 30000, 280000),
(12, 'EMP012', '2026-09', 215000, 65000, 27000, 253000),
(13, 'EMP013', '2026-09', 250000, 80000, 32000, 298000),
(14, 'EMP014', '2026-09', 480000, 160000, 62000, 578000),
(15, 'EMP015', '2026-09', 195000, 58000, 24000, 229000),
(16, 'EMP016', '2026-09', 285000, 92000, 36000, 341000),
(17, 'EMP017', '2026-09', 265000, 84000, 34000, 315000),
(18, 'EMP018', '2026-09', 205000, 62000, 26000, 241000),
(19, 'EMP019', '2026-09', 180000, 52000, 21000, 211000),
(20, 'EMP020', '2026-09', 260000, 83000, 33000, 310000)
;

### Performing data analysis using the HR DB
-- Q1. List the full name and state of origin of every employee in the Finance department. Sort the results alphabetically by full name.
SELECT full_name, state_of_origin
FROM biodata
WHERE department = 'Finance'
ORDER BY full_name
;

-- Q2. How many male and how many female employees are in thecompany? Show the gender and the count.
SELECT gender, COUNT(*) AS total
FROM biodata
GROUP BY gender
;
-- Q3. Show the emp_id, kpi_score and rating of every employee rated Outstanding or Exceeds in the 2025 review. Sort by kpi_score from highest to lowest.
SELECT emp_id, kpi_score, rating
FROM performance_details
WHERE rating IN ('Outstanding', 'Exceeds')
ORDER BY kpi_score DESC
;

-- Q4. Show the number of employees in each department. Sort by head count from highest to lowest, then by department name.
SELECT department, COUNT(*) AS headcount
FROM biodata
GROUP BY department
ORDER BY headcount DESC, department
;

-- Q5. Show the full name, department and net pay of every employee whose net pay for pay month 2026-09 was above ₦300,000. Sort by net payfrom highest to lowest.
SELECT b.full_name, b.department, p.net_pay
FROM biodata b
INNER JOIN payroll_details p ON b.emp_id = p.emp_id
WHERE p.pay_month = '2026-09' AND p.net_pay > 300000
ORDER BY p.net_pay DESC
;

-- Q6. For pay month 2026-09, show eachdepartment's number of employees, total net pay and average net pay (rounded to 2decimal places). Sort by average net pay from highest to lowest.
SELECT b.department,
       COUNT(*)                   AS employees,
       SUM(p.net_pay)             AS total_net_pay,
       ROUND(AVG(p.net_pay), 2)   AS avg_net_pay
FROM biodata b
INNER JOIN payroll_details p ON b.emp_id = p.emp_id
WHERE p.pay_month = '2026-09'
GROUP BY b.department
ORDER BY avg_net_pay DESC
;

-- Q7. List the full name, department, kpi_score and training_hours of every employee who was rated below in 2025. Sort by kpi_score from lowest to highest.
SELECT b.full_name, b.department, p.kpi_score, p.training_hours
FROM biodata b
INNER JOIN performance_details p ON b.emp_id = p.emp_id
WHERE p.rating = 'Below'
ORDER BY p.kpi_score ASC
;

-- Q8. For the 2025 reviews, show each rating category with the number of employees in it and the average training hours (rounded to 2 decimal places). Include only rating categories with more than three employees. Sort by average training hours from highest to lowest.
SELECT rating,
       COUNT(*)                     AS employees,
       ROUND(AVG(training_hours), 2) AS avg_training_hours
FROM performance_details
GROUP BY rating
HAVING COUNT(*) > 3
ORDER BY avg_training_hours DESC
;
