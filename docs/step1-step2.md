Step 1: Create an Interactive Resume in HTML
Objective: Build a project-oriented resume in HTML with interactive features.
Date Completed: [Insert date, e.g., March 2025]
Tasks
1.	Drafted a Project-Oriented Resume 
o	Focused on cloud, security, and networking projects to appeal to cloud engineering roles.
o	Highlighted measurable outcomes (e.g., reduced vulnerabilities by 40%, improved response time by 30%).
o	Included sections: Objective, Key Projects, Professional Experience, Education, Certifications, Skills, Additional Information.
2.	Converted to HTML with Interactivity 
o	Created index.html using HTML, CSS, and JavaScript.
o	Added collapsible sections for a cleaner look (e.g., click to expand/collapse Key Projects).
o	Styled with basic CSS (Arial font, blue headers, hover effects).
o	Tested locally in a browser to confirm functionality.
Outcome
•	Produced index.html, a static resume page with interactive collapsible sections.
•	File size: 6.2 KB.
Technologies Used
•	HTML, CSS, JavaScript.
________________________________________
Step 2: Host the Resume on AWS S3 as a Static Website
Objective: Deploy the resume on AWS S3, making it publicly accessible within the Free Tier.
Date Completed: [Insert date, e.g., March 2025]
Tasks
1.	Created an S3 Bucket 
o	Bucket Name: fareeth-m-resume-2025.
o	Region: eu-west-2 (London) for low latency in the UK.
o	Disabled “Block all public access” to allow public hosting.
o	Kept default settings (no versioning, no logging) to stay within Free Tier.
2.	Uploaded index.html 
o	Uploaded the file to the root of the bucket.
o	File size (6.2 KB) well within Free Tier’s 5 GB storage limit.
o	Used 1 PUT request (within 2,000 free monthly requests).
3.	Set Public Access via Bucket Policy 
o	Added a bucket policy to grant public read access (ACL disabled due to “bucket owner enforced” setting): 
json
CollapseWrapCopy
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicRead",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::fareeth-m-resume-2025/*"
        }
    ]
}
o	Ensured the site is accessible to the public.
4.	Enabled Static Website Hosting 
o	In bucket Properties, enabled static website hosting.
o	Set Index document to index.html.
o	Noted the endpoint URL: http://fareeth-m-resume-2025.s3-website-eu-west-2.amazonaws.com.
o	Used minimal GET requests (within 20,000 free monthly requests) and data transfer (within 15 GB free limit).
5.	Tested the Site 
o	Accessed the endpoint URL in a browser.
o	Confirmed the resume loaded with working collapsible sections.
Outcome
•	Successfully hosted the resume on S3 as a static website.
•	Publicly accessible at: http://fareeth-m-resume-2025.s3-website-eu-west-2.amazonaws.com.
•	Stayed within AWS Free Tier limits (no charges incurred).
Technologies Used
•	AWS S3.
Challenges Faced
•	Initially couldn’t set public access via ACL due to “bucket owner enforced” setting.
•	Resolved by adding a bucket policy to grant public read access.

