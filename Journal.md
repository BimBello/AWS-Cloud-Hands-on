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

Then to configure the actions, I selected "In alarm", "create a new topic" and entered (Hands_on_Billing_Alert) as my topic. 


