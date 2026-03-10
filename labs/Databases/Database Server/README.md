<h1>BUILDING A DB SERVER AND INTERACT WITH IT USING AN APP</h1>
<h2>Objectives</h2>
After completing this lab, I can:
<ol>-Launch an Amazon RDS DB instance with high availability</ol>
<ol>-Configure the DB instance to permit connections from my web server</ol>
<ol>-Open a web application and interact with my database</ol>
<h2>Task 1: Create a security group for the RDS DB instance</h2>
<p>In this task, I will create a security group to allow my web server to access my RDS DB instance. The security group will be used when i launch the database instance.</p>
<p>In the AWS management console: Services menu> VPC> Networking and content delivery. In the left navigation pane i click "security groups" then "create security group"</p>


<h2>Task 2: Create a DB subnet group</h2>
<p>In this task, I will create a DB subnet goup that is used to tell RDS which subnets can be used for the database. Each DB subnet requires subnets in atleast two availability zones.</p>
<p>Services menu> RDS> database. In the left navigation pane I click "subnet groups" then "create subnet"</p>


<h2>Task 3: Create an Amazon RDS DB instance</h2>
<p>In this task, I configure and launch a MULTI-AZ Amazon RDS for mysql database instance.</p>
<p>In the left navigation pane I click "databases" then "create database"</p>


<p>Task 4: Interact with the database</p>
<p>In this task, I will open a web application running on my web server and configure it to use the database.</p>
