# How to Host a Static Website Using Amazon S3 

This project shows you how to use Amazon S3 to host a simple static website. It’s a great way to publish HTML, CSS, and images online — without needing a web server.

Amazon S3 (Simple Storage Service) is part of AWS, and it can store your website files and serve them through a web link. It’s free for small projects if you stay within the AWS Free Tier (5 GB storage for 12 months).  
📷 `screenshots/aws-free-tier.png`  
https://github.com/user-attachments/assets/4b9de909-3433-4794-a32f-26d25ac108d5

S3 is also cheap. If we go to the official S3 Pricing page, we can see the storage and bandwidth costs are low for most users.  
📷 `screenshots/s3-pricing.png`  

---

**Open S3 in AWS Console**  
First, log in to the AWS Console. In the search bar, type **S3** and click on it.

📷 `screenshots/01-aws-s3-dashboard.png`

---

**Create a Bucket**  
Click **Create bucket**.  
Give it a unique name (like `my-site-name`) — every bucket name must be unique worldwide.  

📷 `screenshots/02-create-bucket.png`  
📷 `screenshots/03-bucket-name.png`

It automatically chooses your selected region — for me, it was **Cape Town (af-south-1)**.  
Just scroll and create. No need to change anything else.

---

**Turn On Static Website Hosting**  
Once the bucket is created, go to the **Properties** tab.  
Scroll down to **Static website hosting** and click **Edit**.  

Choose **Enable: Host a static website**, and set the **Index document** as `index.html`. Then click Save.

📷 `screenshots/04-enable-static-hosting.png`  
📷 `screenshots/05-set-index-document.png`

After saving, scroll down again to the **Static website hosting** section — you’ll see the web hosting endpoint.  
📷 `screenshots/endpoint-visible.png`  

Try opening that link in the browser — at first, it gives a **403 Forbidden** error.  
📷 `screenshots/403-forbidden.png`  

To fix this, we need to make the bucket public.

---

**Allow Public Access**  
By default, your bucket blocks public access.  

Go to the **Permissions** tab, find **Block public access**, and click **Edit**.  
Uncheck “Block all public access” and confirm the warning.  

This will make your files viewable on the internet.

📷 `screenshots/06-block-public-access.png`

---

**Add a Bucket Policy**  
Next, go to **Bucket Policy** under the Permissions tab.  

Click **Edit** and paste the policy that gives everyone read access to your files.  

📷 `screenshots/07-edit-bucket-policy.png`

✅ You can find the full JSON code in `bucket-policy.json` in this project.

---

**Upload Your Website Files**  
Now go to the **Objects** tab and click **Upload**.  

Add your `index.html` file and any other files like images or CSS.

📷 `screenshots/08-upload-files.png`  
📷 `screenshots/09-file-list.png`

---

**Open Your Website**  
After everything is set up, go back to the **Static website hosting** section.  

You’ll see your **Endpoint** — that’s your live website link.  
Click it to view your site in the browser.

📷 `screenshots/10-access-website.png`  
📷 `screenshots/11-site-preview.png`

---

## What’s Included

- `index.html` – Simple web page  
- `bucket-policy.json` – JSON file for public access  
- `screenshots/` – Step-by-step image folder  

---

## Why I Did This

I made this project to practice using AWS and hosting websites on the cloud.  
It’s a beginner-friendly way to learn about static web hosting and AWS permissions.

---

**Thanks for reading! 🙌**
