<h1>BUILDING A DB SERVER AND INTERACT WITH IT USING AN APP</h1>
<h2>Objectives</h2>
After completing this lab, I can:
<ol>-Launch an Amazon RDS DB instance with high availability</ol>
<ol>-Configure the DB instance to permit connections from my web server</ol>
<ol>-Open a web application and interact with my database</ol>
<h2>Task 1: Create a security group for the RDS DB instance</h2>
<p>In this task, I will create a security group to allow my web server to access my RDS DB instance. The security group will be used when i launch the database instance.</p>
<p>In the AWS management console: Services menu> VPC> Networking and content delivery. In the left navigation pane i click "security groups" then "create security group"</p>

<img width="1013" height="392" alt="Screenshot 2026-03-10 152104" src="https://github.com/user-attachments/assets/8531e634-bf07-459a-8903-1a8a65f2b5de" />


<p>Then I add inbound rules</p>

<img width="1272" height="228" alt="Screenshot 2026-03-10 152255" src="https://github.com/user-attachments/assets/6f6d5109-67a5-4c2e-b39c-d114ffd52a57" />

<img width="639" height="55" alt="Screenshot 2026-03-10 152346" src="https://github.com/user-attachments/assets/18aee07b-e64c-4558-be9c-2450676c2515" />


<h2>Task 2: Create a DB subnet group</h2>
<p>In this task, I will create a DB subnet goup that is used to tell RDS which subnets can be used for the database. Each DB subnet requires subnets in atleast two availability zones.</p>
<p>Services menu> RDS> database. In the left navigation pane I click "subnet groups" then "create subnet"</p>

<img width="1146" height="466" alt="Screenshot 2026-03-10 152555" src="https://github.com/user-attachments/assets/35dc0e5c-08c4-4adf-85d3-a081a042aa29" />

<p>Then I add subnets</p>

<img width="888" height="402" alt="Screenshot 2026-03-10 152749" src="https://github.com/user-attachments/assets/c507c5d2-277c-4c59-953c-439421e2c3ab" />

<img width="1042" height="281" alt="Screenshot 2026-03-10 152819" src="https://github.com/user-attachments/assets/dd66fea7-bd88-4c71-8494-92cc25af9f72" />

<h2>Task 3: Create an Amazon RDS DB instance</h2>
<p>In this task, I configure and launch a MULTI-AZ Amazon RDS for mysql database instance.</p>
<p>In the left navigation pane I click "databases" then "create database"</p>

<img width="1078" height="374" alt="Screenshot 2026-03-10 154548" src="https://github.com/user-attachments/assets/e540c388-9ea7-4e52-80f9-1e1afb4ce98b" />

<p>Task 4: Interact with the database</p>
<p>In this task, I will open a web application running on my web server and configure it to use the database.</p>

<img width="1184" height="454" alt="Screenshot 2026-03-10 155440" src="https://github.com/user-attachments/assets/be6f0b91-828f-4c69-bed1-f6c3ceb99767" />
