<h1>CREATING NETWORKING RESOURCES IN AN AMAZON VIRTUAL PRIVATE CLOUD(VPC)</h1>
<h2>Objective</h2>
In this lab I will:
<p>Create a VPC, Internet Gateway, Route Table, Security Group, Network Access List, and EC2 instance to create a routable network within the VPC</p>
<h2>Scenario</h2>
<p>My role is a Cloud Support Engineer at Amazon Web Services (AWS). During my shift, a customer from a startup company requests assistance regarding a networking issue within their AWS infrastructure.</p>
<h3>Task 1: Investigate the customer's needs</h3>
<p>For this task i will investigate the customer's request and build a VPC that has network connectivity.</p>

<h3>STEP 1: Create a VPC</h3>
<p>I navigate to the top left corner, and select <b>VPC</b> under <b>Networking and Content Delivery</b> in the Services navigation pane. I navigate to the top right corner, and select <b>Create VPC</b>.</p>

![WhatsApp Image 2026-02-19 at 11 09 17](https://github.com/user-attachments/assets/d31da391-e865-4c07-8424-961424532199)

<h3>STEP 2: Create a subnet</h3>

<p>Now that the VPC is complete, I look at the left navigation pane and select <b>Subnets</b>. In the top right corner,I select <b>Create subnet.</b></p>

![WhatsApp Image 2026-02-19 at 11 11 41](https://github.com/user-attachments/assets/7098baed-a8f8-4af2-9f55-06e33ce44810)

<h3>STEP 3: Create a route table</h3>

<p>I navigate to the left navigation pane, and select <b>Route Tables</p>. In the top right corner I select <b>Create route table</b>.</p>

![WhatsApp Image 2026-02-19 at 11 19 13](https://github.com/user-attachments/assets/93c1feb8-e69c-4067-b031-67bf565ad40b)

<h3>STEP 4: Create an internet gateway</h3>

<p>From the left navigation pane,  I select <b>Internet Gateways</b>. I create an Internet Gateway (IGW) by selecting <b>Create internet gateway</b> at the top right corner.></p>


![WhatsApp Image 2026-02-19 at 11 22 54](https://github.com/user-attachments/assets/1cdfdcab-6d30-4400-b52a-4c7c71aec189)

<h3>STEP 5: Attach internet gateway to VPC</h3>

<p>Once created,I attach the Internet Gateway to the VPC by selecting <b>Actions</b> at the top right corner and clicking <b>Attach to VPC</b>.</p>

![WhatsApp Image 2026-02-19 at 11 25 07](https://github.com/user-attachments/assets/a637b978-280c-4981-b5c6-ce791120f215)

<h3>STEP 6: Add route to route table</h3>

![WhatsApp Image 2026-02-19 at 11 31 08](https://github.com/user-attachments/assets/ea28715f-b965-4caf-bfb0-9d3e717fdad1)

<h3>STEP 7: Associate subnet to route table</h3>

![WhatsApp Image 2026-02-19 at 11 33 40](https://github.com/user-attachments/assets/d9425cd1-2666-48b9-8426-db385b92fc28)

<h3>STEP 8: Create security group</h3>

![WhatsApp Image 2026-02-19 at 11 38 38](https://github.com/user-attachments/assets/993e6728-788f-42d1-a8ad-568b84c97f1c)

<p>The completed security group is shown below. This indicates that for Inbound rules I am allowing SSH, HTTP, and HTTPS types of traffic, each of which has its own protocols and port range. The source from which this traffic reaches my instance can be originating from anywhere.</p>

![WhatsApp Image 2026-02-19 at 11 42 24](https://github.com/user-attachments/assets/7329b8c7-8419-4d47-a5e3-70daf69a2658)

<h2>Task 2: Launch EC2 instance and SSH into instance</h2>

<p>In this task i will launch an EC2 instance within my public subnet and test connectivity by running the command ping. This will validate that my infrastructure is correct, such as security groups and network ACLs, to ensure that they are not blocking any traffic from my instance to the internet and vice versa. This will validate that i have a route to the internet gateway via the route table and that the internet gateway is attached.</p>

<h3>STEP 1: Launch an EC2 Instance</h3>

![WhatsApp Image 2026-02-19 at 11 51 19](https://github.com/user-attachments/assets/debe700e-5abb-493c-a2c9-3af11d9906b0)

<h3>STEP 2: SSH into the instance</h3>

<h2>Task 3: Use ping to test internet connectivity</h2>
<p>I run the Ping google.com command to test internet connectivity.</p>

<b>I am getting replies back, that means that I have connectivity.</b>
