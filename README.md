# 🚀 CI/CD Project #1 — Static Website Deployment (AWS S3 + CloudFront + GitHub Actions)

This project is a fully automated CI/CD pipeline built using GitHub Actions, Amazon S3, and Amazon CloudFront.
Whenever code is pushed to the repository from the terminal, the workflow:

1. Builds the static website automatically

2. Uploads the updated files to an S3 bucket

3. Invalidates the CloudFront cache  

4. Ensures the latest version is instantly live    

This is all done within seconds of a git push.  

# 🧠 What I Learned

How to host static websites on AWS S3  

How to use CloudFront as a CDN for low latency and HTTPS  

How to automate deployments with GitHub Actions  

IAM permissions, bucket policies, Origin Paths, and access troubleshooting  

How to fix common S3/CloudFront issues like 403 Forbidden 

# 🛠️ Tech Stack

- HTML / CSS

- Git / GitHub

- GitHub Actions

- AWS S3

- AWS CloudFront

- IAM

- Bash / CLI  

# 📂 Deployment Architecture 

GitHub Repo → GitHub Actions → S3 Bucket → CloudFront → User  

# 🔐 IAM Permissions

The pipeline uses a restricted IAM user with least privilege access, including:

- s3:PutObject - Allows GitHub to upload or add a file to the S3 Bucket.

- s3:DeleteObject - Allows GitHub to delete a file inside the S3 Bucket

- s3:ListBucket - Allows GitHub to View file names inside the bucket eg index.html

- cloudfront:CreateInvalidation - As CloudFront caches the S3 files, if GitHub updates a file, CloudFront still shows the old cached versionm so this forces CloudFront to rmeove the old one and pull the new one immediately.  

All essential permissions for a deployment IAM role for CloudFront & a static page on S3.

# 📸 Screenshots

## Home page (Static Page)

![HomePage]

## CI/CD Successful Pipeline

![Pipeline]

# 🧩 Future Improvements

- Custom domain with Route 53

- Add dark mode

- Add animations

- Replace static site with React + CI/CD

