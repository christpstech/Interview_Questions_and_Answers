### **SQL Server Interview Questions and Answers**

#

1. **What Is SQL Profiler?**

   > MS SQL Profiler is a tool provided by Microsoft for **_monitoring and capturing events in SQL Server databases_**. It helps _analyze performance, identify slow queries, and view executed queries and stored procedures_.

2. **What is recursive stored procedure?**

   > Recursive stored procedure is a database procedure that **_calls itself during execution_**. It's used for solving problems with repetitive or nested operations. It allows for iterative processing by repeatedly calling itself with modified parameters until a specific condition is met.

   ```
   CREATE PROCEDURE CalculateFactorial
              @Number INT,
              @Factorial INT OUTPUT
          AS
          BEGIN
              IF @Number = 0
                  SET @Factorial = 1;
              ELSE
              BEGIN
                  DECLARE @PreviousFactorial INT;
                  EXEC CalculateFactorial @Number - 1, @PreviousFactorial OUTPUT;
                  SET @Factorial = @Number * @PreviousFactorial;
              END
          END
   ```

3. **What are the differences between local and global temporary tables?**

- **Local Temporary Tables:**

  > - Scope limited to the current session.
  > - Automatically dropped when the session ends.
  > - Prefixed with a single hash (#) symbol in their name.
  > - Used for temporary data storage within a session.

- **Syntax**
  ```
  CREATE TABLE #<tablename>
  ```
- **Global Temporary Tables:**
  > - Visible to all sessions within the same database.
  > - Automatically dropped when the last session referencing them ends.
  > - Prefixed with a double hash (##) symbol in their name.
  > - Used when multiple sessions need to share temporary data.
- **Syntax**
  ```
  CREATE TABLE ##<tablename>
  ```

4. **What is sub query and its properties?**

   > A sub-query is a query which can be **_nested inside a main query_** like Select, Update, Insert or Delete statements.

   **Note:**

   - A sub query should not have order by clause
   - A sub query should be placed in the right hand side of the comparison operator of the main query
   - A sub query should be enclosed in parenthesis because it needs to be executed first before the main query
   - More than one sub query can be included

   **Syntax:**

   ```
   SELECT EmployeeName
   FROM Employees
   WHERE DepartmentID = (
       SELECT DepartmentID
       FROM Departments
       WHERE DepartmentName = 'IT'
   )
   ```
