<h1>INTRODUCTION TO AWS IDENTITY AND ACCESS MANAGEMENT (IAM)</h1>
<img width="588" height="297" alt="image" src="https://github.com/user-attachments/assets/2de3e9f3-25db-4766-9632-0c9e4d72d268" />
<h2>Objective</h2>
<p>In this lab i should be able to:</p>
<ul>-Create and apply an IAM password policy</ul>
<ul>-Explore pre-created IAM users and user groups</ul>
<ul>-Inspect IAM policies as applied to the pre-created user groups</ul>
<ul>-Add users to user groups with specific capabilities active</ul>
<ul>-Locate and use the IAM sign-in URL</ul>
<ul>-Experiment with the effects of policies on service access</ul>
<h1>Task 1: Create an account password policy</h1>
<p>In this task,I create a custom password policy for my AWS account. This policy affects all the users associated with the account.</p>
<h2>STEP 1</h2>
<p>I note the region. In the AWS Management Console, in the search  box, enter IAM and select it. In the left navigation pane, i choose account settings then change password policy.</p>

![WhatsApp Image 2026-02-26 at 17 19 19](https://github.com/user-attachments/assets/d21fd7f3-55a9-4e82-8515-ea14ee74b872)

<p>I strengthened the password requirements by creating a custom password policy. The various password options that I selected have now made the passwords that the users create much more difficult to crack</p>
<h1>Task 2: Explore users and user groups</h1>
<p>In this task, I explore the users and user groups that have already been created for me in IAM.</p>
<p>I am  able to view pre-created users along with the pre-created user groups. I learn about the attached polices to the user groups and what the differences between the user groups and their permissions are.</p>

<h1>Task 3: Add users to user groups</h1>
<h2>STEP 1: Add user-1 to the S3-Support group</h2>

![WhatsApp Image 2026-02-26 at 17 34 50](https://github.com/user-attachments/assets/adc93a7a-a180-4fa7-8afc-2a079a9d6a62)
<h2>STEP 2: Add user-2 to the EC2-Support group</h2>

![WhatsApp Image 2026-02-26 at 17 35 40](https://github.com/user-attachments/assets/c48d9b93-838b-4b8d-b5fc-c71d33b072f7)
<h2>STEP 3: Add user-3 to the EC2-Admin group</h2>

![WhatsApp Image 2026-02-26 at 17 36 25](https://github.com/user-attachments/assets/fa5f2169-859f-4b4a-85e5-264282205ad5)

<p>I've added all the associated users to the user groups.</p>

<h1>Task 4: Sign in and test user permissions</h1>
<p>In the left navigtion pane, u choose "dashboard", i copy th "sign-in URL for IAM users in this account"</p>

![WhatsApp Image 2026-02-26 at 17 38 06](https://github.com/user-attachments/assets/d1cc4303-6ebd-4bd3-a64b-9bdda2b45625)

<p>I paste the URL into a private window, then sign in as user 1 who has been hired as my amazon s3 storage support staff.</p>
<p><b>NB: YOUR LOGIN CREDENTIALS SHOULD BE CONFIDENTIAL. DO NOT SHARE THEM WITH ANYONE!</b></p>

![WhatsApp Image 2026-02-26 at 17 44 30](https://github.com/user-attachments/assets/5e79bb7d-f6d9-42ff-aa06-9c11b02ef55c)

<p>From the Services menu,I choose S3. Choose the name of one of mybuckets, and browse the contents. Because my user is part of the s3 support group in IAM, they hav permission to view the list of s3 buckets and their contents.</p>

![WhatsApp Image 2026-02-26 at 17 48 41](https://github.com/user-attachments/assets/a4255a9a-a4f7-4ea2-99f6-d1471f0e80a3)

<p>However, my user has not been assigned any permissions to use amazon ec2 therefore they cannot see any instances.</p>

![WhatsApp Image 2026-02-26 at 17 50 18](https://github.com/user-attachments/assets/54accd53-51a4-4591-928a-2145042e8594)

<p><b>I repeat the same login process for users 2 and 3.</b></p>
<p>User 2 can see EC2 instances because they have read-only permissions. However, they cannot make any changes to the amazon ec2 resources. I cannot stop the instance because the policy gives me permission to only view information and does not give me permission to make changes</p>
<p>User 3 is an administrator therefore they have permissions to stop the EC2 instance</p>

<h1>Conclusion</h1>
<p>I Created and applied an IAM password policy,
Explored pre-created IAM users and user groups,
Inspected IAM policies as applied to the pre-created user groups,
Added users to user groups with specific capabilities active,
Located and used the IAM sign-in URL, and
Experimented with the effects of policies on service access</p>


