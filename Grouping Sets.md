## Exercise:

#### Question:

##### Calculate the total amount of employees per department using grouping sets
###### Database: Employees
###### Table: Employees

#### Solution:


```python
select grouping(e.dept_no), e.dept_no, COUNT(e.emp_no)
FROM public.dept_emp as e
GROUP BY
	GROUPING SETS (
		(e.dept_no),
     		()
	)
order by e.dept_no
```


#### Question:

##### Calculate the total average salary per department and the total using grouping sets
###### Database: Employees
###### Table: Employees

#### Solution:
```python

select grouping(de.dept_no), de.dept_no, AVG(e.salary)
FROM public.salaries as e
JOIN public.dept_emp as de USING (emp_no)
GROUP BY
	GROUPING SETS (
		(de.dept_no),
     	()
	)
order by de.dept_no
```