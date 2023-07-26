# Stored-Procedures
Learning resource for SQL stored procedures as used in Microsoft SQL Server Management Studio



Stored procedures are typically found within the database management system, not in the C# code in Visual Studio. A stored procedure is a precompiled collection of one or more SQL statements that are stored in the database and can be executed as a single unit.
In most cases, you will create and manage stored procedures using the database management tool or interface provided by the database system you are using (e.g., SQL Server Management Studio for Microsoft SQL Server, phpMyAdmin for MySQL, pgAdmin for PostgreSQL, etc.). These tools offer graphical interfaces where you can write and edit stored procedures.
The process of creating a stored procedure involves writing the SQL code for the procedure, which defines the operations you want to perform in the database. Once created, the stored procedure is stored within the database itself, and you can execute it from your C# code or any other programming language by calling its name.
In your C# code in Visual Studio, you would typically make use of ADO.NET or an ORM (Object-Relational Mapping) library like Entity Framework to interact with the database and execute the stored procedures.
Here's a general overview of how it works:
Create the stored procedure: Use the database management tool to write the SQL code and save it as a stored procedure in the database.
Call the stored procedure from C#: In your C# code, use ADO.NET or an ORM to connect to the database and call the stored procedure by its name, passing any required parameters.
Database executes the stored procedure: When the stored procedure is called from the C# code, the database management system executes the precompiled SQL statements defined in the stored procedure.
Results returned (if any): The stored procedure may perform various operations on the database, and it can also return results or output parameters back to the C# code for further processing.
Remember that the specific steps and syntax may vary depending on the database management system and programming framework you are using, but the basic concept of stored procedures remains consistent.


In Microsoft SQL Server Management Studio (SSMS), you can access stored procedures using the Object Explorer and the Query Editor. Here's a step-by-step guide to accessing stored procedures in SSMS:
Connect to the Database: Open SQL Server Management Studio, and connect to the SQL Server instance where your database is hosted. Enter your server name, authentication credentials, and click "Connect."
Expand the Database: In the Object Explorer window (usually located on the left side of SSMS), expand the node for the database where your stored procedures are located. Click on the "+" icon next to the database name to reveal its objects.
Navigate to Stored Procedures: Within the expanded database node, find the "Programmability" or "Programmable Objects" folder. This folder contains various programmable objects, including Stored Procedures, Functions, etc. Click on the "+" icon next to "Programmability" to expand it.
View Stored Procedures: After expanding the "Programmability" folder, you will see a sub-folder labeled "Stored Procedures." Click on the "+" icon next to "Stored Procedures" to view a list of all stored procedures in the database.
Inspect Stored Procedure: To inspect the details of a specific stored procedure, find and click on its name in the list. The right-hand pane of SSMS will display the definition and properties of the selected stored procedure.
Modify or Execute Stored Procedure: From the right-hand pane, you can modify the stored procedure's code or execute it directly by clicking the "Execute" button. Executing a stored procedure in SSMS will execute its code on the database server, and any results or messages will be displayed in the "Results" pane.
Please note that modifying or executing stored procedures through SSMS requires appropriate permissions on the database server. Ensure that you have the necessary privileges before making any changes.
Using this approach, you can explore, modify, or execute stored procedures in Microsoft SQL Server Management Studio effectively.

Procedure Template (Microsoft SQL Server Management Studio)

-- =======================================================
-- Create Stored Procedure Template for Azure SQL Database
-- =======================================================
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
-- =============================================
# SET ANSI_NULLS ON:

#The SET ANSI_NULLS option determines how NULL values are treated during comparisons in SQL operations.
#When SET ANSI_NULLS is set to ON, comparisons involving NULL values follow the ANSI SQL standard behavior. It means that any comparison involving NULL (e.g., NULL = NULL, NULL <> NULL, etc.) will return neither true nor #false but instead will result in an unknown result, denoted by NULL.
#By default, this option is set to ON, and it is recommended to keep it that way to ensure consistent behavior across different SQL implementations and comply with ANSI standards.
#SET QUOTED_IDENTIFIER ON:

#The SET QUOTED_IDENTIFIER option allows the use of double quotes (") to define identifiers (e.g., table names, column names, etc.) in addition to the standard SQL Server identifier delimiters, square brackets ([]).
#When SET QUOTED_IDENTIFIER is set to ON, you can enclose identifiers in double quotes, and they will be treated as regular identifiers by SQL Server.
#By default, this option is set to OFF, and it is recommended to turn it ON when using any identifiers with double quotes, especially when working with scripts that may need to be compatible with other database systems.
#GO Statement:

#The GO statement is not a T-SQL statement; rather, it is a batch separator used in SQL Server Management Studio and other SQL Server tools to separate and execute batches of T-SQL commands.
#In SQL Server Management Studio, you can execute multiple batches of T-SQL commands at once. Each batch is separated by the GO keyword. When you execute a script containing GO, the SQL Server Management Studio sends each #batch one by one to the SQL Server for execution.
#It's important to note that GO is not a T-SQL statement recognized by the SQL Server itself; it is only understood by SQL Server Management Studio or other SQL Server tools.
#In summary, the provided lines of code are used to set specific database options for a stored procedure. SET ANSI_NULLS ON ensures that NULL comparisons follow the ANSI SQL standard, and SET QUOTED_IDENTIFIER ON allows #the use of double quotes for identifiers in addition to square brackets. The GO statement is used to separate batches of T-SQL commands when executing scripts in SQL Server Management Studio.
-- =============================================
-- Author:      <Author, , Name>
-- Create Date: <Create Date, , >
-- Description: <Description, , >
-- =============================================
CREATE PROCEDURE <Procedure_Name, sysname, ProcedureName>
(
    -- Add the parameters for the stored procedure here
    <@Param1, sysname, @p1> <Datatype_For_Param1, , int> = <Default_Value_For_Param1, , 0>,
    <@Param2, sysname, @p2> <Datatype_For_Param2, , int> = <Default_Value_For_Param2, , 0>
)
AS
BEGIN
    -- SET NOCOUNT ON added to prevent extra result sets from
    -- interfering with SELECT statements.
    SET NOCOUNT ON

    -- Insert statements for procedure here
    SELECT <@Param1, sysname, @p1>, <@Param2, sysname, @p2>
END
GO



