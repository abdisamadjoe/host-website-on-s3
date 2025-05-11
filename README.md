# How to Host a Static Website Using Amazon S3 

This project shows you how to use Amazon S3 to host a simple static website. It’s a great way to publish HTML, CSS, and images online — without needing a web server.

Amazon S3 (Simple Storage Service) is part of AWS, and it can store your website files and serve them through a web link. It’s free for small projects if you stay within the AWS Free Tier (5 GB storage for 12 months).  

<img src="https://github.com/user-attachments/assets/4b9de909-3433-4794-a32f-26d25ac108d5"/>

S3 is also cheap. If we go to the official S3 Pricing page, we can see the storage and bandwidth costs are low for most users.  

<img src="https://github.com/user-attachments/assets/9295a58e-14ea-48a6-885e-85d06c431b1b"/>

---

## Open S3 in AWS Console  
First, log in to the AWS Console. In the search bar, type **S3** and click on it.

<img src="https://github.com/user-attachments/assets/ddadddab-c164-43a6-a8c3-4a5a0cb46893"/>

---

**Create a Bucket**  
Click **Create bucket**.  
Give it a unique name (like `mystaticwebsite-joe`) — every bucket name must be unique worldwide.  

<img src="https://github.com/user-attachments/assets/8e12d42f-3c37-4cf1-a397-a2de8f3dab25"/>
<br>
<img src="https://github.com/user-attachments/assets/1e5885a3-86dd-4dd2-9eba-1cd51c05e6bf"/>


It automatically chooses your selected region — for me, it was **Cape Town (af-south-1)**.  
Just scroll and create. No need to change anything else.

---

**Turn On Static Website Hosting**  
Once the bucket is created, go to the **Properties** tab.  
Scroll down to **Static website hosting** and click **Edit**.  

Choose **Enable: Host a static website**, and set the **Index document** as `index.html`. Then click Save.

<img src="https://github.com/user-attachments/assets/f8d1d8fe-74fd-4570-9ca4-cddb2694aa51"/>

After saving, scroll down again to the **Static website hosting** section — you’ll see the web hosting endpoint.  

<img src="https://github.com/user-attachments/assets/2ab84c0a-9fc8-427b-b64d-828547cadfcd"/>  

Try opening that link in the browser — at first, it gives a **403 Forbidden** error.  

<img src="https://github.com/user-attachments/assets/08e2a25b-cca7-4ef1-8720-32529ca7a073"/> 

To fix this, we need to make the bucket public.

---

**Allow Public Access**  
By default, your bucket blocks public access.  

Go to the **Permissions** tab, find **Block public access**, and click **Edit**.  
Uncheck “Block all public access” and confirm the warning.  

This will make your files viewable on the internet.

<img src="https://github.com/user-attachments/assets/6ed51a99-4fb6-43cf-a7b7-2df9e787ab76"/>

---

**Add a Bucket Policy**  
Next, go to **Bucket Policy** under the Permissions tab.  

Click **Edit** and paste the policy that gives everyone read access to your files.  

<img src="https://github.com/user-attachments/assets/12a25f93-64a2-46b3-8ea8-ebf1f06e6449"/>

✅ You can find the full JSON code in `bucket-policy.json` in this project.

---

**Upload Your Website Files**  
Now go to the **Objects** tab and click **Upload**.  

Add your `index.html` file and any other files like images or CSS.

<img src="https://github.com/user-attachments/assets/e5b20056-0e6c-487b-a8b0-b54ac74f493f"/>


---

**Open Your Website**  
After everything is set up, go back to the **Static website hosting** section.  

You’ll see your **Endpoint** — that’s your live website link.  
Click it to view your site in the browser.

<img src="https://github.com/user-attachments/assets/15374ea9-c095-4821-9c8d-e06c580a347d"/>


---


## Why I Did This

I made this project to practice using AWS and hosting websites on the cloud.  
It’s a beginner-friendly way to learn about static web hosting and AWS permissions.

---

**Thanks for reading! 🙌**
