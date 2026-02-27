<h1>MALWARE PROTECTION USING AN AWS NETWORK FIREWALL</h1>
<H2>Lab Overview</H2>
<p>Malware, short for malicious software, refers to any intrusive software developed by cybercriminals (often called hackers) to steal data and damage or destroy computers and computer systems. Examples of common malware include viruses, worms, Trojan horses, spyware, adware, and ransomware. Firewalls are like physical security walls situated between an organization's internal network and any external public networks such as the internet. The firewall protects an internal network from access by unauthorized users on an external network. Users need access to the internet for business reasons, but they can inadvertently download malware, which can impact network and data security. Malware threats can be present, and organizations can use various techniques and services to mitigate these threats (for example, firewalls, antivirus software, and user control best practice). This lab focuses on countermeasure techniques using a firewall.</p>
<h2>Scenario</h2>
<p>AnyCompany has hired me as a new security engineer, and the company has tasked me with hardening the company’s security perimeter. There have been reports of users accidentally downloading malware after accessing specific websites. The IT team for AnyCompany has provided me with the URLs of the sites hosting the malware. It is my job to find a solution to mitigate access to these malicious actor files.</p>
<h2>Objective</h2>
<p>After this lab i should be able to:</p>
<ol>-Update a network firewall</ol>
<ol>-Create a firewall rules group</ol>
<ol>-Verify and test that access to malicious sites is blocked</ol>
<h2>Lab Environment</h2>
<p>In this lab, I have a pre-configured TestInstance (Amazon Elastic Compute Cloud [Amazon EC2]) instance to use to test access to the website hosting malicious files. This is contained in a perimeter zone and separated from the rest of AnyCompany’s important servers. I update the AnyCompany network firewall, create a rules group, and then attach that rules group to a firewall policy and the network firewall itself. I then log into the TestInstance and test the remediation. All backend components, such as Amazon EC2, AWS Identity and Access Management (IAM) roles, and some AWS services, have been built into the lab already.</p>
<h1>Task 1: Confirm Reachability</h1>
<p>In this task, I log into the EC2 instance TestInstance that has been pre-configured during lab setup. From there, I issue a wget command to the malicious actor files that the IT team provided to me to confirm reachability. I confirmed that the URL hosting the malware files is accessible through the current network and network firewall that AnyCompany is using. I used an isolated TestInstance EC2 instance to run commands and download the same malicious files that users downloaded. I now need to fix the AnyCompany network firewall to stop access to this site.</p>

<img width="1321" height="602" alt="image" src="https://github.com/user-attachments/assets/b83aa8ab-96aa-4123-a25f-3edd4f269007" />

<h1>Task 2: Inspect the network firewall</h1>
<p>In this task, I inspect the network firewall and update the firewall policy. I then update the firewall policy to forward all packets for stateful rule inspection.</p>
<h3>STEP 1: Configure the firewall policy</h3>
<p>Firewall> Overview> FirewallPolicy</p>

<img width="1080" height="180" alt="image" src="https://github.com/user-attachments/assets/0444f382-8c73-4da4-bd34-6d79dd3ce127" />
<img width="1072" height="486" alt="image" src="https://github.com/user-attachments/assets/176a0bc4-4cd5-43b5-8a38-3ea5bf8cb7c6" />


<h1>Task 3: Create a firewall rule group</h1>
<p>In this task, I create a stateful network firewall rule group that uses Suricata rules. Once I attach this rule group to the network firewall, it blocks the malicious websites that AnyCompany users accessed.</p>
<p>Network firewall rule groups> create network firewall rule group</p>

<img width="1325" height="461" alt="image" src="https://github.com/user-attachments/assets/6c6ad9b2-cbc6-47d1-a9f4-f923021ef378" />

<h1>Task 4: Attach a rule group to the network firewall</h1>
<p>In this task, I attach the network firewall rule group that i created in the network firewall.</p>
<p>Firewalls> labfirewall> labfirewall policy> stateful rule groups> add unmanaged stateful rule groups</p>

<img width="1056" height="198" alt="image" src="https://github.com/user-attachments/assets/90800080-7b4f-41d5-91b0-d831fa6202cc" />

<h1>Task 5: Validate the solution</h1>
<p>In this task, I log back into the TestInstance to test that the network firewall properly blocks attempts to access the malicious website files.</p>

<img width="1323" height="287" alt="image" src="https://github.com/user-attachments/assets/bdc2ebf9-bbd9-4a3e-ad68-6396db0fa6be" />

CHOOSE CONNECT AND THEN CONNECT UNDER SESSION MANAGER

<img width="996" height="374" alt="image" src="https://github.com/user-attachments/assets/0cc4682d-1f59-42e1-83f9-9046ce0aa61e" />

<p>I've verified that the network firewall has been updated and configured properly to block the malicious websites. I've confirmed that access is blocked by logging into the TestInstance EC2 instance and running wget commands to these files. Users are now unable to access these malicious files from this website.</p>

