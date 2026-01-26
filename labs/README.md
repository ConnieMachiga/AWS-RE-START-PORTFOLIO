⦁	OBJECTIVE
Amazon EC2 provides a wide selection of instance types optimized to fit different use cases.  comprise varying combinations of CPU, memory, storage, and networking capacity and give you the flexibility to choose the appropriate mix of resources for your applications. Each instance type includes one or more instance sizes so that you can scale your resources to the requirements of your target workload.
⦁	Topics covered:
Launched a web server with termination protection enabled
Monitored my EC2 instance
Modified the security group that my web server is using to allow HTTP access
Resized my Amazon EC2 instance to scale
Tested termination protection
Terminated my EC2 instance
###TASK1- Launching my EC2 instance
Search for ec2 instance in the navigation bar search box then in the search result under services i click ec2
 <img width="1160" height="342" alt="image" src="https://github.com/user-attachments/assets/f71c2538-3a8a-4046-abdd-a36a2cab04b5" />

In the left navigation pane i click instances, there are no instances running therefore i launch an instance by clicking "LAUNCH INSTANCES" in orange
 <img width="1350" height="295" alt="image" src="https://github.com/user-attachments/assets/e5041332-d3a7-4678-8934-8416299b9fbc" />

In step 1 of task , I name my instance. In the Name and tags pane, in the Name text box,I  enter Web Server. I scroll down then locate the Application and OS Images (Amazon Machine Image) pane. Under AMI Machine Image (AMI),I  notice that the Amazon Linux 2023* image is selected by default therefore I keep the setting as instructed. i scroll down the page and choose an istance type. From the dropdown,I select t3.micro.
 <img width="1158" height="440" alt="image" src="https://github.com/user-attachments/assets/2dcabaf0-013b-4f53-a366-fb20cb66d7c6" />

I then select a key pair. In the Key pair (login) pane, I select Proceed without a key pair (Not recommended). After selecting a key pair, I configure the network settings, as displayed in the picture below. In the Network settings pane, choose Edit.For VPC - required, select Lab VPC. Still in the Network settings pane, configure the Security Group as follows:
Security group name - required: Web Server security group
Description: Security group for my web server
 <img width="829" height="248" alt="image" src="https://github.com/user-attachments/assets/dae83527-5d6f-466c-a5d5-462691d19de3" />

 
In the Configure storage pane,I keep the default storage configuration.
I then expand the advaned details pane, select the dropdown for termination protection then choose enable. Paste the commands [copied from the instructions] into the user data text box.
 <img width="575" height="257" alt="image" src="https://github.com/user-attachments/assets/3ca92b8a-41a7-46d7-817b-6e10c4c50807" />

I scroll down, in the right pane, i click launch instance then view all instance and would you look at that! My instance is running.
 <img width="1348" height="234" alt="image" src="https://github.com/user-attachments/assets/555f80ea-fc30-4ade-baca-e81941b2c097" />

###TASK 2- Monitor my instance
Instance is running, status checks passed 
<img width="1340" height="549" alt="image" src="https://github.com/user-attachments/assets/26f5fe9f-f3ed-46b6-ab0c-248542e50a01" />

.###TASK 3- Updating security group and access the web server
I Select the instance by checking the box and select the Details tab, copy the Public IPv4 address of my instance to my clipboard. I copy the IP address in a new tab and press enter. I cannot access the web server because the security group is not permitting inbound traffic on port 80, which is used for HTTP web requests. As shown in the image below.
 <img width="578" height="494" alt="image" src="https://github.com/user-attachments/assets/681b59c7-b270-428e-ac17-87123da5b614" />

This means that i need to permit inbound traffic by adding rules. I easily accessed then under web server security group panel. The type should be HTTP and source should be anywhere IPv4. I then save the rules. My security group now permits HTTP traffic into my Amazon EC2 Instance.
 <img width="1344" height="397" alt="image" src="https://github.com/user-attachments/assets/91b3104b-f133-440d-a907-6348583f724d" />

Below is the reloaded IP address that coud not load in the previous step due to inbound rules not permitted.
 <img width="431" height="44" alt="image" src="https://github.com/user-attachments/assets/ce77e917-4da4-400c-80d7-119621bc8294" />

###TASK 4- Resizing my EC2 instance
I cannot resize an ec2 instance while it is running so I have to stop it. Under my instances, I check web server in the check box> instance state> stop instance. My instance has stopped.
 <img width="1115" height="247" alt="image" src="https://github.com/user-attachments/assets/1d75cc5d-4054-43d6-a3dd-e1d139dbc330" />

 Time to change the instance type from t3.micro to t3.small. Actions dropdown menu> instance settings> change instance type
 <img width="394" height="287" alt="image" src="https://github.com/user-attachments/assets/dacfb46d-15e3-49fe-ab3f-2f61099a190b" />

Now I have to resize the EBS volume. I select volumes located under Elastic Block Store. Check volume box>actions.Modify volume.
 <img width="669" height="365" alt="image" src="https://github.com/user-attachments/assets/93ca879a-4387-4af8-822f-855916c6aded" />

i then start my instance
###TASK 5- Test Termination protection
The instance did not terminate and a red error message pops up at the top that says: Failed to terminate an instance: The instance may not be terminated. This is because it has termination protection enabled.
 <img width="1081" height="97" alt="image" src="https://github.com/user-attachments/assets/40e58f03-0328-4f72-a02a-1a201a9dac51" />

When this happens, i need to disable termination protection In the Actions  menu, select Instance settings  Change termination protection.

 <img width="614" height="390" alt="image" src="https://github.com/user-attachments/assets/9428ffec-d2c0-47fa-ad28-d1ff466b16e8" />

When this is done, I terminate the instance. In the Actions  menu, select Instance State  Terminate instance.
 
<img width="1078" height="186" alt="image" src="https://github.com/user-attachments/assets/5a323f28-a893-49f6-8b1d-b4b78f154ff6" />

All done. My instance has been terminated



 
