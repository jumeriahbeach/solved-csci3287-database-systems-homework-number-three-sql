Download Link: https://assignmentchef.com/product/solved-csci3287-database-systems-homework-number-three-sql
<br>
<h1>Overview</h1>

This assignment will give you hands-on practice in working with MySQL and the SQL language.  In this Project you will create a database and populate it with data using the scripts provided.  You will use the database you create for running a variety of queries and answering a few questions.

<h1>Objectives</h1>




<ol>

 <li>Become familiar with the SQL language &amp; syntax for SELECT queries, DDL and DML</li>

 <li>Become familiar with a tool of your choice for building and submitting queries (whether command mode or GUI.)</li>

 <li>Successfully run the scripts necessary to create a sample database, verify that your database is correctly built.</li>

 <li>Run SQL queries against your database to answer the assigned problems.</li>

</ol>




<h1>StepOne:Downloading   and  Installing MySQL</h1>

For this project assignment you will need to download and install MySQL on your computer. How you do this will depend on what type of computer you have and what Operating System it is running.




You will want to download <strong>MySQL Community Server 8.0.*</strong>  The current release number changes from time to time. As of this writing, the most recent release is 8.0.17.  If for some reason you don’t want to use version 8.0 – for example if you already have version 5.7 running on your computer, you can use version 5.7.x.   Either version will work fine.




Do <strong>NOT</strong> download “MySQL Cluster” software — similar name, but a <strong><em>VERY</em></strong> different DBMS product.




This page (below) contains online documentation links where you can find help with the download and installation if you need it.




The download you need can be found here:  <u>https://dev.mysql.com/downloads/mysql/</u>

Choose the download file that matches your computer’s OS and version.

Once you have downloaded and installed MySQL, you should launch the MySQL instance so that it is running in the background on your computer.

<h1>Step Two:          Choose     Your Preferred          Query       Editor       Tool</h1>

In order to create SQL queries and run them against your MySQL database, you will need a tool or a user interface through which you can create and execute queries, and then view/copy/export the answer set.




The default is the mysqld command line interface. This command line interface is installed with MySQL and is similar to using the Linux shell. If you choose to do your queries via the MySQL command line interface, you do not need to download/install any query tool.




However, managing and running queries against MySQL databases is simpler, faster and easier if you use a GUI (graphic user interface) tool. There are many available.




You can use <strong>MySQL Workbench</strong>. You have seen your instructor use MySQL Workbench in class to create an ERD (Entity Relationship Diagram) data model and then generate SQL to create tables. MySQL Workbench is free. You can use MySQL Workbench to build and submit queries against your database. It is available here: <u>https://dev.mysql.com/downloads/workbench/</u>  MySQL offers versions for Windows, Linux, MAC.

A great open source alternative is <strong>DBeaver</strong>. The community edition is free and it comes with versions for many different OS builds and works fine with MySQL. <u>https://dbeaver.io/download/</u>




Another alternative for MAC users is <strong>DataGrip</strong>. <u>https://www.jetbrains.com/datagrip/</u> They offer a free 30-day trial, and a special free edition for students that you can sign up for.




<strong>         </strong>

<h1>Step Three:      Creating   the   Database</h1>




Once you have selected your query editor, you need to download the “ClassicModelsCreate” script file from Moodle, unzip it and execute it.  It will create your database and tables, and then load the tables with data.  The script runs fine as-is without any modification.




Before you can create your database, you need to make sure that your instance of MySQL is running in the background.




Then using your query editor, you must connect to the running MySQL instance prior to running the script.




HINT:   You should download and print this ERD (below) and keep it handy when you are writing your queries. It is very helpful to have table and column names in front of you when writing SQL queries.




<h1>MySQL      Sample     Database Schema</h1>

The MySQL sample “Classic Models” database schema consists of the following tables:

<table width="603">

 <tbody>

  <tr>

   <td width="117"><strong>Customers</strong></td>

   <td width="486">stores customer data.</td>

  </tr>

  <tr>

   <td width="117"><strong>Products</strong></td>

   <td width="486">stores a list of scale model cars.</td>

  </tr>

  <tr>

   <td width="117"><strong>ProductLines</strong></td>

   <td width="486">stores a list of product line categories.</td>

  </tr>

  <tr>

   <td width="117"><strong>Orders</strong></td>

   <td width="486">stores sales orders placed by customers.</td>

  </tr>

  <tr>

   <td width="117"><strong>OrderDetails</strong></td>

   <td width="486">stores sales order line items for each sales order.</td>

  </tr>

  <tr>

   <td width="117"><strong>Payments</strong></td>

   <td width="486">stores payments made by customers based on their accounts</td>

  </tr>

  <tr>

   <td width="117"><strong>Employees </strong></td>

   <td width="486">stores all employee information as well as the organization structure such as who reports to whom.</td>

  </tr>

  <tr>

   <td width="117"><strong>Offices</strong></td>

   <td width="486">stores sales office data.</td>

  </tr>

 </tbody>

</table>




<strong> </strong>

<strong> </strong>

<strong>Note:  </strong>GUI Query Editor Users: After you run some queries to create your tables, you might expect the new tables to immediately appear under the “object explorer” on the left side of your GUI query editor. They will eventually show up, but to see them appear right away, you will need to click on the “refresh” icon (if your tool has one.) If this icon does not appear, then click somewhere within your “object explorer” and the newly created tables should appear. (Depends on your query tool…)




If you are using the command line editor, you can enter SHOW TABLES and MySQL will show you all the tables in your database.




After running the unzipped script file to create and load your database, you should run the following “Verify” script to ensure that your database is built correctly.

Verify Script:

SELECT table_schema, table_name, table_rows

FROM information_schema.tables

WHERE TABLE_SCHEMA LIKE ‘classic%’;




You should see the following tables and row counts for your Classic Models database.

<table width="290">

 <tbody>

  <tr>

   <td width="107"><strong>table_schema </strong></td>

   <td width="94"><strong>table_name </strong></td>

   <td width="89"><strong>table_rows </strong></td>

  </tr>

  <tr>

   <td width="107">classicmodels</td>

   <td width="94">customers</td>

   <td width="89">122</td>

  </tr>

  <tr>

   <td width="107">classicmodels</td>

   <td width="94">employees</td>

   <td width="89">23</td>

  </tr>

  <tr>

   <td width="107">classicmodels</td>

   <td width="94">offices</td>

   <td width="89">7</td>

  </tr>

  <tr>

   <td width="107">classicmodels</td>

   <td width="94">orderdetails</td>

   <td width="89">2996</td>

  </tr>

  <tr>

   <td width="107">classicmodels</td>

   <td width="94">orders</td>

   <td width="89">326</td>

  </tr>

  <tr>

   <td width="107">classicmodels</td>

   <td width="94">payments</td>

   <td width="89">273</td>

  </tr>

  <tr>

   <td width="107">classicmodels</td>

   <td width="94">productlines</td>

   <td width="89">7</td>

  </tr>

  <tr>

   <td width="107">classicmodels</td>

   <td width="94">products</td>

   <td width="89">110</td>

  </tr>

 </tbody>

</table>




<h1>Preparing         Your Assignment      Submission</h1>

Your results for this homework assignment should be captured in a document (such as a .txt file, MS Word or similar tool.)   Please then save your final deliverable document as a <strong>PDF</strong>. Your submission should be a document saved and submitted as a PDF file via the link found in the assignment section of the “Week 6 Moodle September 30 – October 6” — which is the same place where you found this file.




You must turn in BOTH your SQL Code and your ANSWER SET (unless otherwise specified.)

For each problem where a multi-row answer set is created, the number of rows you should expect in your answer set is listed in parentheses after the problem/question. Some queries will product NO answer set.




<h1>Query       Problems</h1>




For this project you must create and execute queries against the ClassicModels database to fulfill the requirements listed below. For each query requirement, as a “hint”, the number of rows to expect in your answer set is listed in parentheses.




<ol>

 <li>List the names of the cities in alphabetical order where Classic Models has offices. (7)</li>

</ol>




<ol start="2">

 <li>List the EmployeeNumber, LastName, FirstName, Extension for all employees working out of the Paris</li>

</ol>

office. (5)




<ol start="3">

 <li>List the ProductCode, ProductName, ProductVendor, QuantityInStock and ProductLine for all products with a QuantityInStock between 100 and 1000. (10)</li>

 <li>(Use a SUBQUERY) List the ProductCode, ProductName, ProductVendor, BuyPrice and MSRP for the least expensive (lowest MSRP) product sold by ClassicModels. (“MSRP” is the Manufacturer’s Suggested</li>

</ol>

Retail Price.)  (1)

<ol start="5">

 <li>What is the ProductName and Profit of the product that has the highest profit (profit = MSRP minus BuyPrice). (1)</li>

 <li>List the country and the number of customers from that country for all countries having more than ten customers. List the countries sorted in descending order from highest to lowest number of customers. Title the column heading for the count of customers as “Customers”. (3)</li>

 <li>List the ProductCode, ProductName, and number of orders for the product with the most orders. Title the column heading for the count of orders as “OrderCount”. (1)</li>

 <li>List the EmployeeNumber, Firstname + Lastname (concatenated into one column in the answer set, separated by a blank and referred to as ‘name’) for all the employees reporting to Diane Murphy or William Patterson. (5)</li>

 <li>List the EmployeeNumber, LastName, FirstName of the president of the company (the one employee with no boss.) (1)</li>

 <li>List the ProductName for all products in the “Classic Cars” product line from the 1970’s. (7)</li>

 <li>List the month name and the total number of orders for the month in 2005 in which ClassicModels customers placed the most orders. (1)</li>

 <li>List the firstname, lastname of employees who are Sales Reps who have no assigned customers. (2)</li>

 <li>List the customername of customers from Germany with no orders. (10)</li>

 <li>List the customername and total quantity of products ordered for customers who have ordered more than 1700 products across all their orders. (6)</li>

 <li>Create a NEW table named “TopCustomers” with three columns: CustomerNumber (integer),</li>

</ol>

ContactDate (DATE) and  OrderTotal (a decimal number with 9 digits in total having two decimal places).

None of these columns can be NULL.  Include a PRIMARY KEY constraint named “TopCustomer_PK” on

CustomerNumber. (no answer set)




<ol start="16">

 <li>Populate the new table “TopCustomers” with the CustomerNumber, today’s date, and the total value of all their orders (PriceEach * quantityOrdered) for those customers whose order total value is greater than $140,000. (inserted 10 rows, no answer set)</li>

</ol>




<ol start="17">

 <li>List the contents of the TopCustomers table in descending OrderTotal sequence. (10)</li>

</ol>




<ol start="18">

 <li>Add a new column to the TopCustomers table called OrderCount (integer). (No answer set)</li>

</ol>




<ol start="19">

 <li>Update the Top Customers table, setting the OrderCount column to a random number (from 0 to 18). (Should update 10 rows) HINT:  use the RAND() and FLOOR() functions.</li>

</ol>




<ol start="20">

 <li>List the contents of the TopCustomers table in descending OrderCount sequence. (10)</li>

</ol>




<ol start="21">

 <li>Drop the TopCustomers table. (no answer set)</li>

</ol>











