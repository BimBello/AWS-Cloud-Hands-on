## AWS Simple Storage service

### Task 15- Create an S3 Bucket

Before i commenced this task, I downloaded Notepad ++, index.html and error.html files and also some PNG files.

On the AWS managment console, enter S3 on the search window and click "Create Bucket". I named my bucket "handsonbucket1" ,selected an AWS region, ACL enabled and I left others default then Create Bucket.
I opened the newly created bucket to add files and upload. I browsed a PNG image already saved on my laptop to upload. I opened the uploaded file, copied the object URL but because the bucket and object were not made public, I got an error message.    <img width="589" alt="S3 object error message" src="https://user-images.githubusercontent.com/124819387/226461924-f748d80a-c8cd-4c9c-a261-37d9c5dd4c38.PNG">


To make this bucket object public, I went back to my bucket, clicked Permissions and unchecked the "Block all public access and saved changes to confirm the action.
Also go back to the uploaded PNG object to make public. Check the object box, from "Action" dropdown, make public using ACL.  <img width="547" alt="S3 object public" src="https://user-images.githubusercontent.com/124819387/226462197-7c5e9703-50ab-4cf8-8d93-4b7b3e2fdfc3.PNG">

I refreshed the URL and now i can see my bucket object   <img width="624" alt="S3 public object seen" src="https://user-images.githubusercontent.com/124819387/226462645-b920116b-3cb2-404c-9206-d488749dc830.PNG">


## Task 16 - Add Bucket Policy

I went back to my Bucket and clicked permissions on the "Edit Bucket policy page, copied the URL and pasted on my notepad++ and added /* to the URL. This allows everyone to see the content of my bucket.
I went to policy generator and slected "S3 Bucket policy" from the type of policy drop down.
Effect- Allow
Principal - * (this allows all)
Actions- Get Object
ARN- (Paste the copied arn from the notepad, next is Add statement then generate policy.   <img width="813" alt="Generated policy" src="https://user-images.githubusercontent.com/124819387/226464690-d8511361-c90e-4e11-9531-4d93fea81330.PNG">


<img width="355" alt="Generated policy 1" src="https://user-images.githubusercontent.com/124819387/226464474-f98fd6d3-2913-42b6-a9d5-9b9e5d321267.PNG">

I copied and pasted the generated policy on the Edit policy page and saved changes. To check if the policy is in effect, I repeated the process of adding and uploading a file from the S3 bucket page, uploaded another PNG file then copied the URL to paste on a new browser. This opened the object in the bucket.  <img width="749" alt="s3 AWS logo" src="https://user-images.githubusercontent.com/124819387/226465851-af8f59a3-e99f-4211-ad0e-c7615b836102.PNG">



## Task 17- Uploading a Static Website
From my Bucket, I clicked on Bucket properties, scrolled down to the bottom of the page and edit "static website hosting" and enable "Static website hosting".   <img width="527" alt="static website hosting" src="https://user-images.githubusercontent.com/124819387/226467771-2ed3457b-7714-48f1-82a2-666fbedbf3df.PNG">


I wrote "index.html on the index document and "error.html" on the error document. Saved changes.

Next, to add the index.html (desktop document), I repeated the process of uploading an object, selected the index.html and error.html file previously downloaded.

I went back to my S3 bucket objects and selected the index.html to copy the URL. Paste on a new browser and now the static website can be accessed.  



## Task 18- Enabling Versioning in S3
Versioning means keeping multiple variants of an object in the same bucket.

On AWS management console, I selected my bucket and enabled 'Bucket Versioning" by clicking "Edit". I repeated the process of uploading the index.html and error.html file then enable "show Versions".    <img width="815" alt="versioned objects" src="https://user-images.githubusercontent.com/124819387/226473210-35c526b1-2a06-4387-80e0-f7ecc66fc6b2.PNG">



## Task 19 - Cross Region Replication for S3.
Replication enables automatic asynchronous copying of objects across AWS S3 buckets. Objects can be copied between different AWS regions or within the same region.

Firstly, I created a new bucket "handsonbucket2" and made public.
Then I created another bucket "myhandson-destinationbucket1" for the replication in another region.    <img width="811" alt="Destination Bucket" src="https://user-images.githubusercontent.com/124819387/226470697-6d858d9c-17af-44a8-8714-6620c666c96b.PNG">


I went back to my source bucket, clicked Management then scrolled down to "Replication rule" and create. 

I entered a name and left status enabled. Source bucket- selected "Apply to all objects in the bucket"

For destination, I chose a bucket in this account and browsed the bucket name (myhandson-destinationbucket1) then choose path and enabled object versioning. 
Choose a new IAM role (create new role). I left encryption blank and storage class default then saved  <img width="615" alt="Replication rule" src="https://user-images.githubusercontent.com/124819387/226473024-56d53747-5cad-47cd-8194-62407abc16b1.PNG">


Back to the source bucket, add files and upload. I went back to the replication bucket and it has been replicated. 







