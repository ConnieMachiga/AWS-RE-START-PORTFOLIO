<h1>TROUBLESHOOTING A NETWORK ISSUE</h1>
<h2>Objective:</h2>
After completing this lab i should be able to:
<ol>Analyze the customer scenario</ol>
<ol>Troubleshoot the issue</ol>
<h2>Scenario:</h2>
<p>My role is a cloud support engineer at Amazon Web Services (AWS). During my shift, a consulting company has a networking issue within their AWS infrastructure. The following is the email and an attachment of their architecture:</p>
Hello, Cloud Support!

When I create an Apache server through the command line, I cannot ping it. I also get an error when I enter the IP address in the browser. Can you please help figure out what is blocking my connection?

Thanks!

Ana
Contractor

<img width="832" height="444" alt="image" src="https://github.com/user-attachments/assets/f26cc773-dc2e-494d-81d9-308662f118fa" />

<h1>Task 1: Use SSH to connect to an Amazon Linux EC2 instance</h1>
<p>I opened putty.exe and configured the putty session on windows to connect to Amazon Linux EC2 instance</p>
<h1>Task 2: Install httpd</h1>
<p>I checked the status of the httpd service by entering the <b>"sudo systemctl status httpd.service"</b> command</p>
<p>I started the httpd service by entering the <b>"sudo systemctl start httpd.service"</b> command</p>
<p>The httpd service is now running. It is time to check if it is working. I run the following URL in a new browser tab:http://54.191.93.142</p>
<p>The test page of the Apache HTTP server does not load, as shown in the image below:</p>

<img width="531" height="501" alt="image" src="https://github.com/user-attachments/assets/aff35297-7325-4350-a785-7c7ee0c1d09d" />

<h1>Task 3: Investigate the customer's VPC configuration</h1>
<p>I then investigate the customer's VPC and their resources. I navigate to the AWS management console to check subnets, route tables, internet gateway, security groups and network ACLs. Route tables have the correct routes and are associated with the correct subnets. There is an internet gateway and it is attached. However, i have discovered that the correct security group rules are not configured.</p>
<p>I add inbound rule. Type: HTTP. Source: Anywhere-IPv4</p>

![WhatsApp Image 2026-02-23 at 16 19 11](https://github.com/user-attachments/assets/d7b1685a-a10a-45df-aed1-2a952a7670c9)


<p>I then refresh the web browser in the other tab. After fixing the issue, I was able to successfully load the Apache server.</p>

![WhatsApp Image 2026-02-23 at 16 20 34](https://github.com/user-attachments/assets/540d8741-fac7-42ba-bd62-db4938f7a3da)
