## Task 8- Budget Setup

To set up my billing budget on my free tier account so that I can track my spend, I clicked on "My Account", then "Billing Dashbord.  <img width="373" alt="Billing Dashboard" src="https://user-images.githubusercontent.com/124819387/222807385-6aeaa31c-76f9-4218-aed7-c1dac72218cb.PNG">

Kindly note that because I'm signed in as IAM user BeemBeem, I did not have the permission to access the billing information. So what did I do?
I signed back in my Root account, from "My account", I scrolled down to find "IAM User and Role Access to Billing information" then i activated IAM Access.

I went back to my IAM user account and refreshed the page to see the AWS Billing dashboard.

To set up my budget, I chose a zero spend budget type, entered my email for notification and thats it! Budget set!<img width="817" alt="Budget_alarm" src="https://user-images.githubusercontent.com/124819387/222822550-f70b9a45-2191-412d-a271-9d720a173176.PNG">


## Task 9- Creating a Billing Alarrm; CloudWatch

On my AWS management console, I clicked on "My Account" , then "Billing Dashboard". On the AWS Billing Dashboard page by the left hand side, I clicked on "Billing Preferences" to make a preference on the bill.

I entered my email address, checked the box for "receive free tier usage alerts" and "receive billing alerts" then save preferences. <img width="851" alt="Billing alarm" src="https://user-images.githubusercontent.com/124819387/222898449-e2831ffe-2baf-4ec7-a75e-6c5e2b70ca44.PNG">


Now, to create my billing alarm, I selected the region I'm working from. I chose "us-east-1"

From the search option, I typed in "CloudWatch" and clicked on it.This landed me on the CloudWatch dashboard
On the left hand side of the Billing dashboard, from the options under "Alarms", i clicked on "Billing" and then "Create Alarm" button on the far right.

I followed the steps to create the alarm.

First step- Select metric. I selected "Billing", then "Total Estimated Charge".

I selected USD currency,  and select Metric. This takes us to the page that provides all the information related to the metrics.

I left the conditions for Threshold type as static and >threshold Greater. Howevever, I set my threshold value at $5 limit so that when my charges goes greater than $5, I will be notified.

Then to configure the actions, I selected "In alarm", "create a new topic" and entered (Hands_on_Billing_Alert) as my topic, then added a name and description then Create alarm.   <img width="942" alt="Billing Alert" src="https://user-images.githubusercontent.com/124819387/222914911-5dae7db8-11bd-40dd-b52f-e27ba4222970.PNG">



## Task 10- Creating a Windows EC2 Instance

On my management consule, I searched for EC2 in search option and landed on the EC2 dashboard.

Clicked on "Instances" followed by "Launch Instance".

I named my instance "Hands-on-Windows-Instance-1" and selected the Windows AMI (Amazon Machine Image). <img width="612" alt="AMI type" src="https://user-images.githubusercontent.com/124819387/222917141-9a96ae42-425d-4fcb-a601-d52075b13aa9.PNG">


Next, for Instance type,  I selected a Free-tier eligible Microsoft windows server 2022 base. I selected the t2.mirco because of its 1vCPU and 1GB of memory   <img width="596" alt="Instance Type" src="https://user-images.githubusercontent.com/124819387/222917260-e4e9da7a-31cb-46b8-bad6-51f3690c8561.PNG">

I clicked on View all instances to see my running instance.  <img width="842" alt="Running instances" src="https://user-images.githubusercontent.com/124819387/222918244-0934fcbe-517e-4ccb-9251-495dc5a79395.PNG">


Now, creating a Key Pair adds an extra layer of security to my instance and also enables me access my instance remotely. Also, AWS provides the facility of public and private keys and the secret key must be kept in a private place in the system. 

To create a Key pair, I clicked on "Create a new Key pair" and selected "pem" as the key file format and it is used with open SSH. Once i clicked on "create key pair", my key pair was downloaded on my local system.

I left the Network settings and storage options as default and launched my instance.   <img width="664" alt="Launched instance" src="https://user-images.githubusercontent.com/124819387/222918123-937e9d87-aae2-4a79-838f-ff9eafc90f4c.PNG">


## Task 11- Connect the Instance
Checked the box on new running instance and I clicked on "Connect"   <img width="774" alt="Connect instance" src="https://user-images.githubusercontent.com/124819387/222918474-ef7e9aaf-f73b-4905-b9bb-3a26b6caf911.PNG">

Next, select "RDP Client" and download the remote desktop file and  click on "Get password". Remember the key pair i downlaoded earlier? I uploaded it with the "Upload private key file" button, which brought up some encrypted messages.   <img width="568" alt="uploaded key pair" src="https://user-images.githubusercontent.com/124819387/222919039-a53061bc-8705-4d45-9ccd-359882d637e3.PNG">

After Decrypting, the password appears!
I Copied the password, and went back to downloaded instance (Key pair), right clicked and connect. Paste the copied password on the Administrator credentials pop up and and OK. Voila!!! My first windows remote desktop connection!    ![RDP desktop](https://user-images.githubusercontent.com/124819387/222919846-cfa3b7dd-029e-4846-8aac-ed3c34287e60.jpg)



## Task 12 Configure Webserver Internet Information Service (IIS) on Windows EC2 Machine

This a Microsoft web server that runs on Windows operating system and is used to exchange static and dynamic web content with internet users. IIS can be used to host, deploy, and manage web applications.

From my EC2 server, right click on the windows icon and select "server manager". Click on "Add roles  and features". Skip the default wizard page and also keep the "Role baded or feature based installation" on default. Click "Next, select "Server Roles" on the left hand side and select "Web server (IIS) from the option.
Click on Add features- Management console and next! Install and the Inetpub is created and saved on C drive of the desktop folder.   <img width="523" alt="IIS download" src="https://user-images.githubusercontent.com/124819387/224694278-8240d0e2-4943-4407-9316-3c965f5cd74d.PNG">


The webserver will be in the Inetput file (wwwroot).
To access the server with IIS, go back to your instance on AWS console, copy the public IP address and paste it on a new windows tab (http://ip address). I ensured that my port range 80 is open or added to my security group so that I can access the default IIS page.  <img width="893" alt="IIS Default page" src="https://user-images.githubusercontent.com/124819387/224694433-c7bd2745-368d-4002-9236-8bdc8810eefe.PNG">


To confirm my IIS windows server is functioning, from the wwroot folder, I opened on notepad, deleted all the command, then pasted a simple HTMl code and refreshed the windows page.  <img width="800" alt="HTML webserver example" src="https://user-images.githubusercontent.com/124819387/224695341-33caa34c-ad7e-4fe7-bec3-033c8615734c.PNG">


## Creating Linux Machine on AWS

















