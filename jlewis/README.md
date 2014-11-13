# SQL
Structured Query Language (SQL) is a language designed for managing and working with data in a relational database management system. The original version, called SEQUEL (Structured English Query Language), was developed at IBM in the 70s by a research team working on a relational database model. The database and language were never officially released, but the language became very popular. It became commercially available in the 1979 version of Oracle's RDMS.

### Purpose
SQL is both a data definition language and a data manipulation language. It is set based and mostly declarative, but also includes procedural elements such as variables, control blocks, control flow and conditionals. These procedural extensions are generally provided by the database system vendor and are specific to their RDMS. The most popular are Transact-SQL for MS SQL Server and PL/SQL for Oracle's RDMS. There is also an ANSI standard called SQL/PSM. These extensions provide a way to create functions and stored procedures. 

It is a high-level (4GL), and the database engine parses the language, performs optimization, and then executes the statements. It appears to work very similar to Java or C#, with an intermediate language that is executed, instead of a pure interpreted situation.

The following language rules are for the ANSI standard implementation in MySQL 5.0 or greater.

### Scoping
SQL uses block level, static scoping as well as dynamic global and session scope for variables that can be set at runtime. Session variables are loosely typed and remain in scope throughout the client session or connection to the server. Block level variables remain in scope within the block (BEGIN...END). Variables and control flow must appear within blocks. Blocks can be nested. Blocks can only appear in stored procedures, functions, triggers, and events. Variables must be declared in the initial block and then can be used within nested block statements. Inner block variables will hide outer block variables and no changes will occur to outer block variables of the same name. Local variable names will override table column names within blocks as well.

### Typing
Variables declared with the DECLARE keyword are strongly typed. Table columns are also strongly typed. Session level variables declared using the "@" sign are called user-defined variables and are loosely typed. These variables allow you to pass data from one statement to another. The types used for user-defined variables can only be of these types: integer, decimal, floating-point, binary or non-binary string, or NULL. The coercibility of user-defined variables is implicit. Values of types other than permissible types will be converted to a permissible type. CAST can also be used to convert to a specific data type. 

### Functions/Stored Procedures
User defined functions and store procedures are generally related to a specific database and provide ways to store a set of SQL statements for reuse. This reduces the amount of information sent to the server from the client for evaluation. It can also provide security restrictions so that direct table access is limited and transactions must be submitted through the stored routine.

Functions, like in many procedural languages, provide general purpose computation or database select statements with a return value. There are also many built in server functions to perform things like table aggregation or retrieve the current system date and time.

### Recursion
Stored procedure recursion is possible, but disabled by default because of demands on the thread stack space. Stored functions cannot be recursive.

CREATE PROCEDURE total(IN number INT, OUT result INT)  
BEGIN  
	DECLARE temp INT DEFAULT 0;  
	DECLARE temp2 INT DEFAULT 0;  
	DECLARE tempId INT DEFAULT NULL;  
	SELECT amount from sales_table INTO temp;  
	SELECT parent_id from sales_table INTO tempId;  
  
IF tempId is NULL  
THEN  
	set result=temp;  
ELSE  
	CALL total(tempID, temp2);  
	SET result=temp+temp2;  
END IF;  
END;  
  
CALL total(1, @total);  
SELECT @ total;  


### Arrays
For an RDMS system, an array is a table and is the primary form of storage for the system. A table is a type of two dimensional array of rows and columns.

Example: Get all rows and columns of a table.

Select * from table_name

Example: Get only the "name" column from the table.

Select name from table_name

