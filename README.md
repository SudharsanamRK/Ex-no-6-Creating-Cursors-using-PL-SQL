# Ex. No: 6 Creating Cursors using PL/SQL
## DATE:
### AIM:
To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table:
```
CREATE TABLE emplys (
    empid NUMBER,
    empname VARCHAR(15),
    dept VARCHAR(15),
    salary NUMBER
    );
select * from emplys;
INSERT INTO emplys VALUES (1, 'DEXTER', 'Supervisor', 40000);
INSERT INTO emplys VALUES (2, 'JUSTIN LEE', 'Product Manager', 110000);
```

### Employee table :
![dbms ex-06 out1](https://github.com/SudharsanamRK/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/115523484/e0cffd53-aa3c-42fa-ba65-2186fa501f23)


### PL/SQL Cursor code:
```
 DECLARE
    CURSOR emplys_cursor IS
    SELECT empid, empname, dept, salary
    FROM emplys;
    emp_id NUMBER;
    emp_name VARCHAR(15);
    emp_dept VARCHAR(15);
    emp_salary NUMBER;
    BEGIN
   OPEN emplys_cursor;
   LOOP
   FETCH emplys_cursor INTO emp_id, emp_name, emp_dept, emp_salary;
   EXIT WHEN emplys_cursor%NOTFOUND;
   DBMS_OUTPUT.PUT_LINE('EMPID: ' || emp_id);
   DBMS_OUTPUT.PUT_LINE('EMPNAME: ' || emp_name);
   DBMS_OUTPUT.PUT_LINE('DEPT: ' || emp_dept);
   DBMS_OUTPUT.PUT_LINE('SALARY: ' || emp_salary);
   END LOOP;
   CLOSE emplys_cursor;
   END;
   /
```

### Output:
![dvms ex-06 out2](https://github.com/SudharsanamRK/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/115523484/3bf08619-0671-4ab4-bf54-2dd1139833a8)

### Result:
Thus, To create a cursor using PL/SQL completed successfully.
