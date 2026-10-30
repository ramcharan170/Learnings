# SQLNotes



**CASE Statements in SQL:**<br>
The SQL case Expression is used to add the &nbsp;conditional Logic(IF-THEN_ELSE ) directly into the Sql Queries.<br>

There are 2 Types of Case Statements: <br>

*1. Searched CASE*<br>
This format evaluates the independent boolean Expressions sequentially. It is ideal for grouping the numeric ranges or checking ranges or checking conditions across multiple columns <br>
```
SELECT
    employee_name,
    salary,
    CASE
        WHEN Salary>=10000 THEN 'TIER 1(High)'
        WHEN salary BETWEEN 50000 AND 9999 THEN 'Tier 2 (Mid)'
        ELSE 'Unspecified'
    END AS salary_bracket
FROM employees
```
You can use a CASE Statements to dynamically prioritize the custom sorting Orders rather than defaulting strictly to alphabetical sequence. <br>
```
SELECT employee_name, department, role
FROM employees
ORDER BY 
    CASE 
        WHEN role = 'Director' THEN 1
        WHEN role = 'Manager' THEN 2
        ELSE 3
    END, 
    employee_name ASC;
```
