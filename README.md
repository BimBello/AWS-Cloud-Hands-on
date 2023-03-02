# 60days-of-AWS-Cloud-Hands-on
My AWS Cloud Computing journey

SO I have decided to go on a one-man project journey of learning everything I can possibly learn in AWS cloud computing

I'm staring today, 1st of March 2023 and I hope I'm able to complete all the AWS SAA modules by the end of April because I would love to take the certification exam by then.


## Task 1- Creating an AWS free tier account

I opened a new AWS free tier root account using my email and password. Email was verified, credit card details entered,though not charged .I selected a plan (Basic support- free tier account) and voila! I'm signed up..

I went back to the AWS management console and signed in with my email to begin.


## Task 2- Creating Identity and Access Management(IAM) Users and Groups
My root account was used to create another user account that will be used throughout this hands-on. The root account should be "discarded". Users represents people within the organization and they can be placed in groups. 

To create a user, I went into the IAM console. IAM is a global service.
I created a user (BeemBeem) and created a custom console password. I then created 2 groups (Admin and Cloudprojectgroup) because i need to give permissions. These permissions are assigned JSON documents called policies which helps us define the permissions of the user. I added BeemBeem to the two groups (Admin and Cloudproject) and attached the policy (AdministratorAccess).


To log in with the user BeemBeem, I copied the sign-in URL on my AWS account dashboard and opened another browser so I can log into the management console as BeemBeem.

This takes you to the AWS sign in as IAM user page and I signed in with my 12 digits account ID, BeemBeem as user name and the new password generated in the root account.
<img width="861" alt="IAM user BeemBeem" src="https://user-images.githubusercontent.com/124819387/222528576-f8e22583-e835-4359-b5d5-93b03cbbbeff.PNG">
![IAM_user](https://user-images.githubusercontent.com/124819387/222528584-248effcc-e6a4-43a2-88dc-7864a22e9913.JPG)



## Creating a Multifactor Authentication- MFA

I protected my Root account and IAM user by using a virtual MFA device (Authy).


## AWS Command Line Interface (CLI) Setup on Windows


This is an open source tool that enables one interact with AWS using commands.

I installed CLI version 2 using the MSI installer.
<img width="499" alt="AWS CLI prompt" src="https://user-images.githubusercontent.com/124819387/222527306-92cfbc28-3793-45aa-9726-a1150a742f4e.PNG">


### Installing AWS CLI on Linux
I copied the first code from the AWS page for CLI on Linux and pasted it on my command prompt. Then copied and pasted the 2nd code to unzip my installer then lastly, copied and pasted the last one to run the installer as root.


### Creating Access Keys
From my IAM console, I went to user BeemBeem and under security credentials (scroll down to "create Access Keys").

I selected Command Line Interface (CLI) and created the Access Key which also has a secret key that can be downlaoded aas a csv file.

## Using AWS CloudShell

This is an AWS terminal that can be used to run your commands alternatively to the other CLIs.
 <img width="923" alt="Cloud shell" src="https://user-images.githubusercontent.com/124819387/222526386-d6ba0a62-55a9-4bcc-8146-f4359dd2e71c.PNG">
 




