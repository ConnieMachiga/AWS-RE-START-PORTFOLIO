<h1>WORKING WITH FUNCTIONS</h1>
<h2>Lab Overview & Objectives</h2>
<p>This lab demonstrates how to use some common database functions with the SELECT statement and WHERE clause.</p>
<p><b>After completing this lab, I should be able to:</b>

<ol>Use aggregate functions SUM(), MIN(), MAX(), and AVG() to summarize data</ol>
<ol>Use the SUBSTRING_INDEX() function to split strings</ol>
<ol>Use the LENGTH() and TRIM() functions to determine the length of a string</ol>
<ol>Use the DISTINCT() function to filter duplicate records</ol>
<ol>Use functions in the SELECT statement and WHERE clause</ol></p>
<h2>The following resources are already created for me:</h2>

<img width="540" height="285" alt="image" src="https://github.com/user-attachments/assets/eabf97df-8aa6-4f18-8d23-f10be5a5d667" />

<h2>Scenario</h2>
<p>The database operations team has created a relational database named world containing three tables: city, country, and countrylanguage. Based on specific use cases in the lab exercise, I write a few queries using database functions with the SELECT statement and WHERE clause.</p>
<h3>TASK 1: Connecting to the instance</h3>
<p>In the management console, I search for "EC2" then under instances the check the "command host" instance in the check box. I then connect to it using session manager</p>

<img width="739" height="247" alt="Screenshot 2026-03-10 134519" src="https://github.com/user-attachments/assets/f05302bf-acef-44a5-adc3-b5b69a1f3592" />

<h3>TASK 2: Query the world database</h3>
<p>In this task, I query the world database using various SELECT statements and database functions. I use a function to process and manipulate data in a query. There are a wide range of SQL functions, and this lab reviews a subset of commonly used functions.</p>
<h4>STEP 1</h4>
<P>I enter the "SHOW DATABASES;" command in the terminal to show the existing databases</P>

<img width="411" height="177" alt="Screenshot 2026-03-10 134931" src="https://github.com/user-attachments/assets/82e5e44c-c794-4b51-8eb7-19daf8028280" />

<h4>STEP 2</h4>
<P>I run the "SELECT * FROM world.country;" query to review the table schema, data and number of rows in the country table</P>

<img width="1365" height="400" alt="Screenshot 2026-03-10 135008" src="https://github.com/user-attachments/assets/97a4d493-735a-4a7b-9b3a-973d7aa69e16" />

<P>The following query "SELECT sum(Population), avg(Population), max(Population), min(Population), count(Population) FROM world.country;" demonstrates how to use aggregate functions SUM(), MIN(), MAX(), and AVG() to summarize data. Because the query does not include a WHERE condition, the functions aggregate data from all records in the country table</P>

<img width="1202" height="128" alt="Screenshot 2026-03-10 135042" src="https://github.com/user-attachments/assets/804c2cea-c8b8-49e1-ab75-ec7825b1df85" />

<h4>STEP 3</h4>
<P>Run the "SELECT Region, substring_index(Region, " ", 1) FROM world.country;" query to spilt a string where a space occurs.</P>

<img width="825" height="562" alt="Screenshot 2026-03-10 135115" src="https://github.com/user-attachments/assets/54178e69-6255-4c4b-8e84-65ecada129d1" />

<h1>CHALLENGE</h1>
<p>In this challenge i have to write a query to return rows that have Micronesian/Caribbean as the name in the region column. The output should split the region as Micronesia and Caribbean into two separate columns: one named Region Name 1 and one named Region Name 2.</p>

<img width="1365" height="181" alt="Screenshot 2026-03-10 135208" src="https://github.com/user-attachments/assets/6f42afbe-d0e7-461c-91c9-348eac2573a4" />

<p><b>I achieved this by writing the "SELECT Name, substring_index(Region, "/", 1) as "Region Name 1",substring_index(region, "/", -1) as "Region Name 2" FROM world.country WHERE Region = "Micronesia/Caribbean";" query.</b></p>









