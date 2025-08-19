# Scalable Static Website with S3 🗂️ + Cloudflare 🔒 + GitHub Actions 🚀

This project demonstrates how to deploy a scalable static website using AWS S3, Cloudflare for CDN and HTTPS, and GitHub Actions for continuous integration and deployment (CI/CD).

---
## 📊 Overview
   - This project allows you to host a static website on AWS S3 with global **CDN** (*Content Delivery Network*🌍) and **HTTPS** (*HyperText Transfer Protocol Secure*🔒) using **Cloudflare**.
   - The website is automatically deployed to S3 whenever a commit is made to the `main` branch in GitHub.

---
## ⚙️🔧 Setup
### 📦 Set Up AWS S3
1. **Create an S3 Bucket**:
   - Go to the AWS S3 Management Console
   - Click "Create Bucket" and name it.
   
2. **Enable Static Website Hosting**:
   - Go to the "Properties" tab for your bucket.
   - Scroll to **Static website hosting** and enable it.
   - Set `index.html` as the index document and `error.html` as the error document (if applicable).

3. **Set Bucket Policy**:
   - In the **Permissions** tab, create a bucket policy to allow public read access to your static files.
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::your-bucket-name/*"
         }
       ]
     }
     ```

### 🌐💻 Create Static Website
   - `index.html`: The main entry point of your website.
   - `styles.css`: Your CSS file (optional).
   - `Github Actions`: Create your yml file for Github Actions

**Push to GitHub**: Create a GitHub repository and push your website's code to the repository.
   - Go to GitHub Actions in your repository on GitHub to check if it’s completed ✅

### 🌐⚙️ Configure Cloudflare
1. Create a Cloudflare Account and Add your custom domain to Cloudflare. (**Domain and S3 bucket name must be same**)

2. **Update DNS Records**: In Cloudflare, set up a `CNAME` record to point your custom domain to the S3 bucket:
   - **Type**: `CNAME`
   - **Name**: `www` (or your desired subdomain)
   - **Target**: `Mention your S3 bucket URL`.

3. **Enable SSL**: In Cloudflare, go to the **SSL/TLS** tab and set SSL mode to **Full** or **Full (Strict)** for HTTPS support.

---
### 📱💻 Access the application 
   - Open the application in your browser with domain name
<a href="https://s3deploy.smartsters.ai/" target="_blank">
  <img src="https://img.shields.io/badge/Live%20website-007BFF?style=for-the-badge&logo=githubpages&logoColor=white" alt="Live website Badge" />
</a>


.
