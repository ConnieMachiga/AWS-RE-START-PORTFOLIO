<h1>Scaling And Load Balancing Your Architecture</h1>
<h2>Lab Overview</h2>
<p>In this lab, I use Elastic Load Balancing (ELB) and amazon ec2 auto scaling to load balance and automatically scale my infrastructure.</p>
<h2>If you're wondering what an ELB or auto scaling is:</h2>
<p>ELB automatically distributes incoming application traffic across multiple Amazon Elastic Compute Cloud (Amazon EC2) instances. ELB provides the amount of load balancing capacity needed to route application traffic to help you achieve fault tolerance in your applications.

Auto Scaling helps you maintain application availability and gives you the ability to scale your Amazon EC2 capacity out or in automatically according to conditions that you define. You can use auto scaling to help ensure that you are running your desired number of EC2 instances. Auto scaling can also automatically increase the number of EC2 instances during spikes in demand to maintain performance and can decrease capacity during lulls to reduce costs. Auto scaling is well suited to applications that have stable demand patterns or that experience hourly, daily, or weekly variability in usage.</p>  
<h2>Objectives</h2>
<p>After completing this lab, you should be able to do the following:</p>

Create an AMI from an EC2 instance.

Create a load balancer.

Create a launch template and an Auto Scaling group.

Configure an Auto Scaling group to scale new instances within private subnets.

Use Amazon CloudWatch alarms to monitor the performance of your infrastructure
<h1>Task 1: Creating an AMI for auto scaling</h1>
<p>In this task, I create an AMI from the existing Web Server 1. This action saves the contents of the boot disk so that new instances can be launched with identical content.</p>
<p>In the AWS manageent console , in the search bar, I enter and choose ec2 to open the amazon ec2 management console. In the left navigation pane I locate instances section and choose instances. Web server instance is already created. I select it then in the actions drop down list I choose image and templates then choose create image.</p>

<img width="1284" height="514" alt="Screenshot 2026-03-18 092536" src="https://github.com/user-attachments/assets/aefe5913-f811-4462-b2f2-128b1f6bf95d" />

<h1>Task 2: Creating a load balancer</h1>
<p>In this task, I create a load balancer that can balance traffic across multiple ec2 instances and availability zones.</p>
<p>In the left navigation pane, I locate the Load Balancing section, and choose Load Balancers.I choose Create load balancer.In the Load balancer types section, for Application Load Balancer, I choose Create.

On the Create Application Load Balancer page, in the Basic configuration section,  I configure the following option:

For the Load balancer name, I enter LabELB

In the Network mapping section,I configure the following options:

For VPC, I choose Lab VPC.

For Mappings, I choose both Availability Zones listed.

For the first Availability Zone,I choose Public Subnet 1.

For the second Availability Zone,I choose Public Subnet 2.

These options configure the load balancer to operate across multiple Availability Zones.

In the Security groups section,I choose the X for the default security group to remove it.

From the Security groups dropdown list,I choose Web Security Group.

The Web Security Group has already been created for me, which permits HTTP access.</p>

<p>In the Listeners and routing section,I choose the Create target group link.This link opens a new browser tab with the Create target group configuration options.

On the new Target groups browser tab, in the Basic configuration section, I configure the following:

For Choose a target type,I choose Instances.

For Target group name,I enter lab-target-group</p>

<img width="1310" height="550" alt="Screenshot 2026-03-18 093619" src="https://github.com/user-attachments/assets/3c4f3cd1-fdde-4006-81b7-1ef589779633" />

<p>At the bottom of the page i choose "create load balancer"

<img width="1118" height="266" alt="Screenshot 2026-03-18 094145" src="https://github.com/user-attachments/assets/8aaf1a35-8fa3-47f9-a10a-cec046ec1878" />

<p>To view the LabELB load balancer that I created,I choose View load balancer.To copy the DNS name of the load balancer,I use the copy option , and paste the DNS name into a text editor.</p> 
<h1>Task 3: Creating a launch template</h1>
<p>In this task, I create a launch template for my auto scaling group. A launch template is a template that an Auto Scaling group uses to launch EC2 instances. When you create a launch template, you specify information for the instances, such as the AMI, instance type, key pair, security group, and disks.</p>
<p>At the top of the AWS Management Console, in the search bar, I enter and choose EC2. In the left navigation pane,I locate the Instances section, and choose Launch Templates. I choose Create launch template.

On the Create launch template page, in the Launch template name and description section,I configure the following options:

For Launch template name - required, I enter lab-app-launch-template

For Template version description, I enter A web server for the load test app

For Auto Scaling guidance,I choose  Provide guidance to help me set up a template that I can use with EC2 Auto Scaling.

In the Application and OS Images (Amazon Machine Image) - required section,I choose the My AMIs tab. I Notice that Web Server AMI is already chosen.</p>

<img width="912" height="554" alt="Screenshot 2026-03-18 094712" src="https://github.com/user-attachments/assets/4c9b5d07-069d-470b-b9ca-b855fa72d497" />

<p>In the Instance type section,I choose the Instance type dropdown list, and choose t3.micro.</p>

<img width="888" height="531" alt="Screenshot 2026-03-18 095054" src="https://github.com/user-attachments/assets/2d5e3def-e4a4-4ae0-b388-631d42da263c" />

<p>Under security groups i choose the web security group and then create the launch template</p>

<h1>Task 4: Creating an auto scaling group</h1>
<p>In this task, I use my launch template to create an Auto Scaling group.</p>

<p>Choose  lab-app-launch-template, and then from the Actions  dropdown list,I choose Create Auto Scaling group. On the Choose launch template or configuration page, in the Name section, for Auto Scaling group name,I enter Lab Auto Scaling Group. I then choose Next.</p>

<img width="1017" height="480" alt="Screenshot 2026-03-18 095412" src="https://github.com/user-attachments/assets/ca4ac321-a1ea-46d8-8130-19a55464571c" />

<p>On the Choose instance launch options page, in the Network section,I configure the following options:

From the VPC dropdown list,I choose Lab VPC. From the Availability Zones and subnets dropdown list,I choose Private Subnet 1 (10.0.1.0/24) and Private Subnet 2 (10.0.3.0/24). I Choose Next.

<img width="964" height="477" alt="Screenshot 2026-03-18 095546" src="https://github.com/user-attachments/assets/04749e6c-b2c3-4a56-aa35-cb6808ebb199" />

<p>On the Configure group size and scaling policies – optional page,I configure the following options: 

In the Group size – optional section,I enter the following values: 

Desired capacity:2

Minimum capacity: 2

Maximum capacity: 4

<img width="949" height="428" alt="Screenshot 2026-03-18 095745" src="https://github.com/user-attachments/assets/4770de2a-3cd0-45d2-aa54-ebe13a34726e" />

<p>Auto scaling group is created but then i receive an error due to lab restrictions</p>

<img width="1310" height="202" alt="Screenshot 2026-03-18 100158" src="https://github.com/user-attachments/assets/8156ffc8-5ea6-4e12-b782-17e4fec8b4c2" />

<h1>Task 5: Verifying that load balancing is working</h1>
<p>IN this task, I verify that load balncing is working correctly</p>
<p>In the left navigation pane,I locate the Instances section, and choose Instances.

I see two new instances named Lab Instance. These instances were launched by auto scaling.</p>

<img width="1137" height="325" alt="Screenshot 2026-03-18 100928" src="https://github.com/user-attachments/assets/7ced54a5-3021-4d32-a337-ea0db929b525" />

<p>In the left navigation pane, in the Load Balancing section,I choose Target Groups.I choose lab-target-group. In the Registered targets section, two Lab Instance targets are listed for this target group.</p>

<img width="1073" height="486" alt="Screenshot 2026-03-18 101053" src="https://github.com/user-attachments/assets/0d798b08-0a25-4643-a84f-381cf712011e" />

<p>I open a new web browser tab, paste the DNS name that I copied before, and press Enter.</p.

<img width="1220" height="419" alt="Screenshot 2026-03-18 101639" src="https://github.com/user-attachments/assets/8124bfe9-f457-4da2-97be-fe7e545984b3" />

<p>The Load Test application appears in my browser, which means that the load balancer received the request, sent it to one of the EC2 instances, and then passed back the result.</p>
<h1>Task 6: Terminating the web server 1 instance</h1>
<p>In this task, I terminate the Web Server 1 instance. This instance was used to create the AMI that my Auto Scaling group used, but this instance is no longer needed.</p>

<p>I choose  Web Server 1, and ensure that it is the only instance selected. From the Instance state  dropdown menu,I choose Terminate instance. I Choose Terminate.</p>

<img width="1116" height="249" alt="Screenshot 2026-03-18 102530" src="https://github.com/user-attachments/assets/07deea40-82f2-4592-b226-b4a65a91ee3a" />
