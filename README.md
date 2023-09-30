# Ex. No: 5 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table:
```
CREATE TABLE employee (
  empid NUMBER,
  empname VARCHAR(20),
  dept VARCHAR(20),
  salary NUMBER
);

INSERT INTO employee VALUES (1, 'Jeevapriya', 'Sales', 100000);
INSERT INTO employee VALUES (2, 'Anitha', 'Marketing', 120000);
select * from employee;
```
### Employee table :
![image](https://github.com/SudharsanamRK/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/115523484/c3495ea4-ed0b-4b3a-bb4e-bd5e1241f4c5)


### PL/SQL Cursor code:
```
DECLARE
   CURSOR employee_cursor IS
   SELECT empid,empname,dept,salary
   FROM employee;
   emp_id NUMBER;
   emp_name VARCHAR(50);
   emp_dept VARCHAR(50);
   emp_salary NUMBER;
BEGIN
  OPEN employee_cursor;

  LOOP
    FETCH employee_cursor INTO emp_id, emp_name, emp_dept, emp_salary;

    EXIT WHEN employee_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
    DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
    DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
  END LOOP;

  CLOSE employee_cursor;
END;
/
```

### Output:
![image](https://github.com/SudharsanamRK/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/115523484/35e22690-924c-48bf-ac44-766c5b3ccb2d)

### Result:
Thus, To create a cursor using PL/SQL completed successfully.
