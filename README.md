
Project Documentation: Deploying a Static Website on AWS

1. Introduction
In today's digital age, having an online presence is crucial for businesses, individuals, and organizations. Websites serve as the primary interface between users and the services or information they seek. This project focuses on deploying a static website on AWS, leveraging the power of S3 for hosting and CloudFront for efficient content delivery.

2. Real-life Significance
Scalability: By hosting on AWS S3, the website can handle a vast number of requests. This scalability ensures that as the user base grows, the website remains responsive and available.

Performance: With CloudFront, users experience low latency and high transfer speeds, ensuring a seamless browsing experience. This is especially vital for businesses where user retention is closely tied to website performance.

Cost-Efficiency: Static websites on S3 incur lower costs compared to traditional hosting solutions. You only pay for the storage used and the data transferred, making it a cost-effective solution for startups and SMEs.

Security: Using IAM policies to secure the S3 bucket ensures that the website's content remains protected from unauthorized access or malicious attacks.

3. DevOps Best Practices
Infrastructure as Code (IaC): Automate the creation of the S3 bucket and CloudFront distribution using tools like AWS CloudFormation or Terraform. This ensures repeatability and consistency across deployments.

Continuous Integration and Continuous Deployment (CI/CD): Implement a CI/CD pipeline to automate the deployment of website updates. This ensures that any changes to the website are tested and deployed efficiently.

Monitoring and Logging: Integrate AWS CloudWatch to monitor the health and performance of the S3 bucket and CloudFront distribution. This provides real-time insights and alerts on any potential issues.

Backup and Disaster Recovery: Regularly backup the S3 bucket contents. In case of any unforeseen issues, a recovery plan should be in place to restore the website to its previous state.

Step-by-Step Plan: Deploying a Travel and Tour Website on AWS
1. Preparation
Website Content: Ensure that the static website content for the travel and tour website, including HTML, CSS, JavaScript files, and any images or media, is ready for deployment.
2. AWS Console Access
Login: Access the AWS Management Console using your credentials.
Services: Navigate to the services dropdown and select the required services (S3, IAM, CloudFront).
3. S3 Bucket Creation and Configuration
Create Bucket: In the S3 dashboard, click on "Create Bucket". Name it something relevant, like "travelandtour-website".
Region Selection: Choose a region close to your primary audience for better latency.
Bucket Settings: Leave the default settings but ensure that "Block all public access" is unchecked since this is a public website.
Upload Content: Navigate to the newly created bucket and upload all the website files.
Static Website Hosting: In the bucket properties, enable "Static website hosting". Note the endpoint URL provided; you'll need it for CloudFront.
4. Security with IAM
Create Policy: In the IAM dashboard, create a new policy that allows public read access to the S3 bucket. Use a JSON statement like:
json

{
  "Version": "2012-10-17",
  "Statement": [
      {
          "Effect": "Allow",
          "Principal": "*",
          "Action": "s3:GetObject",
          "Resource": "arn:aws:s3:::travelandtour-website/*"
      }
  ]
}
Attach Policy to Bucket: Go back to the S3 bucket and attach this policy, ensuring public read access.
5. Content Delivery with CloudFront
Create Distribution: In the CloudFront dashboard, click on "Create Distribution".
Web Distribution: Choose "Web" as the delivery method.
Origin Settings: For "Origin Domain Name", select the S3 bucket endpoint URL from the dropdown.
Default Cache Behavior: Accept the default settings but ensure "Redirect HTTP to HTTPS" is enabled for security.
Distribution Settings: Choose a price class based on your target audience. For a global audience, select "Use All Edge Locations".
Deploy: Click on "Create Distribution". Note the CloudFront domain name; this will be the primary URL for accessing the website.
6. Accessing the Website
Once the CloudFront distribution is deployed (it might take some time), you can access the travel and tour website using the unique CloudFront domain name.
7. (Optional) Custom Domain and SSL
If you have a custom domain like "travelandtour.com", you can configure it with Route 53 and attach an SSL certificate using AWS Certificate Manager for a professional touch.
By following this plan, you'll have a travel and tour website hosted on AWS S3, secured with IAM, and delivered efficiently using CloudFront. This setup ensures scalability, performance, and security for your online presence.


# udacitystaticsitewrok
First assignment on DevOps cloud engineering Udacity

s3 url:  http://sem-staticsite.s3-website.us-east-2.amazonaws.com

S3 Buckect name -  sem-staticsite

Cloudfront URL 
https://dgkzby30omhr0.cloudfront.net/


