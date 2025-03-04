# StaticWebsiteS3
s3StaticWebsite in AWS
Description
This project is a simple static website that is hosted on AWS using Amazon S3. It includes HTML, CSS, and JavaScript files. The website is intended to be used as a demonstration of how to host a static website on AWS.

Table of Contents
Installation
Usage
AWS Setup
Deploying to AWS
Contributing
License
Installation
To get started with this project locally, follow these steps:

Clone the repository:

bash
Copy
git clone https://github.com/yourusername/Static3Website.git
Navigate to the project folder:

bash
Copy
cd Static3Website
Open index.html in your browser to view the project locally.

Usage
This static website is simple, and you can make modifications to the index.html, style.css, and script.js files. Once you have made your changes, you can re-upload your files to AWS S3 to reflect the changes online.

index.html: This is the main HTML file for your website.
style.css: This file contains the CSS for the design and layout.
script.js: This file contains the JavaScript used to add interactivity (if any).
AWS Setup
Before deploying to AWS, you need to have an AWS account and configure the following services:

Create an S3 Bucket:

Log in to your AWS Management Console.
Go to S3 under the Services tab.
Create a new bucket with a unique name (e.g., my-static-website-bucket).
Choose a region that is closest to your users.
Set Bucket for Static Website Hosting:

In the S3 console, select your bucket.
Go to the Properties tab.
Under the Static website hosting section, enable the hosting and set the index document to index.html.
You can also set an error document (e.g., error.html) if desired.
Set Bucket Permissions (Public Access):

In the Permissions tab of your bucket, ensure that Block all public access is turned off to allow public access to your static files.
You’ll need to add a Bucket Policy to allow public read access to your files. Here’s an example bucket policy:
json
Copy
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}

Upload Files to S3:

Go to your S3 bucket in the AWS Management Console.
Click Upload, then choose the index.html, style.css, script.js, and any other assets you want to upload (like images).
Ensure that all files are publicly accessible (you can check the "public read" option when uploading or later configure permissions).
Check Website URL:

Once uploaded, go to the Properties tab of your S3 bucket.
Under Static website hosting, you'll find the Website URL.
Open this URL in your browser, and your static website will be live.
Example URL:

arduino
Copy
http://your-bucket-name.s3-website-us-east-1.amazonaws.com
Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Commit your changes (git commit -m "Add new feature").
Push to the branch (git push origin feature-branch).
Open a pull request.
License
This project is licensed under the MIT License - see the LICENSE file for details
