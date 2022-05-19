   QUERIES
  Exploratory Data Analysis 

1. select s.emp_no, e.last_name, e.first_name, e.sex, s.salary
   from employees as e 
   inner join salaries as s on s.emp_no = e.emp_no 
   order by s.emp_no limit 10; 
   
2. select emp_no, last_name, first_name, hire_date 
  from employees where extract(year from hire_date) = 1986;
  
3.select  dm.dept_no,d.dept_name,dm.emp_no,e.last_name,e.first_name,
  from dept_manager as dm inner join departments as d 
  on (dm.dept_no = d.dept_no) 
  inner join employees as e on (dm.emp_no = e.emp_no);

4.select e.last_name, e.first_name from employees as e
   where (e.first_name = 'Hercules') and (lower(e.last_name) like 'b%')
   order by e.last_name;

5.select e.emp_no, e.last_name, e.first_name, d.dept_name from employees as e 
  inner join dept_emp as de on e.emp_no = de.emp_no inner join departments as d 
  on de.dept_no = d.dept_no where lower(d.dept_name) = 'sales' limit 10;

6.select  e.emp_no, e.last_name, e.first_name, d.dept_name from employees as e 
 inner join dept_emp as de on (e.emp_no = de.emp_no) inner join departments as d 
 on (de.dept_no = d.dept_no) where d.dept_name in ('Sales', 'Development') order by e.emp_no limit 12;   

7.select last_name,count(last_name) as Frequency from employees 
group by last_name order by frequency desc;

10.select CONCAT(first_name," ",last_name," ")AS EmployeeName,emp_no,1986-year(hire_date) 
as tenure from employees order by tenure desc limit 10;            


11.1a)select * from salaries where salary>=30000 limit 20;  

2a) select emp_no from employees where left_PPL=1' limit=10;   

3a)SELECT dept_name,COUNT(dept_name) AS Employees_count 
  FROM   employeesmployee GROUP  BY dept_name limit 10;

4)SELECT * FROM employees WHERE FLOOR(EXTRACT(YEAR FROM last_date)*12)-FLOOR(EXTRACT(YEAR FROM hire_date)*12);  ##SQL query to find the employees hired in last n months.

5)select dept_no,count(*),avg(salary) from departments,salaries group by dept_no;
(For each department, retrieve the department number, the number of
employees in the department, and their average salary)
