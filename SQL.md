Refreshing on SQL using the Data Analyst Bootcamp by Alex the Analyst on Youtube

### Basic SQL 
  SELECT statement: Top, Distinct, Count, As, Max, Min, Avg
  &nbsp;
  
  FROM statement: tell SQL which table to pull the data from
  &nbsp;
  
  WHERE statement: =, <>, <, >, <=, >=, And, Or, Like, Null, Not Null, In
  &nbsp;
  
  you can use the wildcard '%' when using Like
    &nbsp;
    
  GROUP BY statement
  &nbsp;
  
  ORDER BY statement

### Intermediate SQL
  Inner join 2 tables = everything in common between both tables
    SELECT *
    FROM table1
    Inner Join table2
    ON table1.id = table2.id

  Full Outer Join = show everything from both tables regardless whether there is a match

  Left Outer Join = take everything from the first table and everything that matches with it from the second table but if anything is only in the second table, it is not included

  Righter Outer Join = take everything from the second table and everything that matches with it from the first table but if anything is only in the first table, it is not included

  Union "stacks" two tables while taking out any duplicates, you need the data to be the same for it to work
    SELECT *
    FROM table1
    UNION
    SELECT *
    FROM table2

  Union all shows all the results and doesn't remove any duplicates

  CASE statement: is an if else statement
    SELECT *
    CASE
      WHEN variable " " THEN " "
      ELSE " "
    END AS " "
    FROM table

  HAVING clause: used when WHERE can't be used with aggregate functions
    SELECT COUNT(jobTitle)
    FROM table1
    GROUP BY jobTitle
    HAVING COUNT(jobTitle) > 1

  UPDATE: updates value in your table
    UPDATE table1  
    SET " "
    WHERE " "

  DELETE: removes entire row from your table
    DELETE FROM table1
    WHERE " "

  Aliasing: temporarily changes column name in your table
    SELECT columnName as Name
    FROM table1

    SELECT columnA + " " + columnB AS columnC
    FROM table1

  Partition by: isolates one specific column you want to aggregate
    SELECT FirstName, LastName, Gender, Salary, 
      COUNT(Gender) OVER (PARTITION BY Gender) as TotalGender
    
### Advanced SQL 

  CTEs: work like sub queries, it is temporary
    WITH CTE_Employee as (SELECT FirstName, LastName, Gender, Salary,
        COUNT(GENDER) over (partition BY Gender) as TotalGender,
        Avg(Salary) OVER (PARTITION BY Gender) as AvgSalary
    FROM table1
    WHERE Salary > '45000)
  
  Now you can select everything from that CTE with the below. The select statement needs to be right below the CTE for it to work
    SELECT *
    FROM CTE_Employee

  Temp Tables: created like a usual table but now you use a #
    CREATE TABLE #temp_Employee (
    EmployeeID int,
    jobTitle varchar(100),
    Salary int
    )

    SELECT *
    FROM #temp_Employee

    Enter an existing table into your temp table:
    INSERT INTO #temp_Employee 
    SELECT *
    FROM table1
    )

    To delete the table and create it again, you use the below query
    DROP TABLE IF EXISTS #Temp_Employee

  String Functions
    SELECT TRIM(columnName) 
    is used to trim the values
    SELECT LTRIM(columnName)
    gets rid of blank spaces on the left side
    SELECT RTRIM(columnName)
    gets rid of blank spaces on the right side

    SELECT REPLACE(columnName, 'whatyouwantreplaced', 'whatyouwanttoreplaceitwith')
    is used to replace values with something else in the table

    SELECT SUBSTRING(columnName, 1, 3)
    this takes parts of columnName starting at the first character and then will have a length of 3
    you can use this when joining two tables when you want to do a "fuzzy match" if the two tables don't have something like an id column for exact matches

    SELECT LOWER(columnName)
    is used to change every character to lower case

    SELECT UPPER(columnName)
    is used to change every character to upper case
      
  
