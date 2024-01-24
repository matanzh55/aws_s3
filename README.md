# aws_s3

S3 Static Website

1. AWS S3 Bucket Creation:

     * Log in to the AWS Management Console:
          Open your web browser and go to the AWS Management Console.
          Sign in with your AWS account credentials.
     * Navigate to the S3 service.
     * Create a new S3 bucket:
          Once you're in the S3 console, click on the "Create bucket" button.
          Configure the bucket:
          Choose a globally unique bucket name (e.g., my-static-website01-bucket in this case).
          Select the region where you want to create the bucket.
          Select "ACLs enabled"
          Turning off block all public access
          Leave other settings as default or configure as needed.
          Review and create- Review your settings and click the "Create bucket" button.

2. Upload Website Files:
    
     Inside your bucket, click on the "Upload" button.
     Select the HTML file that related to the static website. 
     After uploading, select the uploaded file.
     In the "Actions" dropdown, choose "Make public" or configure the permissions to allow public access.
     Review your settings and click the "Upload" button.

3. Configure S3 Bucket for Website Hosting:

     Select the S3 bucket you created for your static website.
     In the bucket details, click on the "Properties" tab.
     Scroll down to the "Static website hosting" card.
     Click on the "Edit" button.
     Choose static website hosting - Enable
     Choose the option for "Host a static website"
     Index document: Enter the main HTML file, e.g., index.html.
     Click the "Save changes" button.
     now you can enter the website through the bucket website endpoint url.

4. Security Best Practices:
     a. Configure Bucket Policy:
          Create a bucket policy that restricts access to the S3 bucket. 
          The "policy.json" is an example of a bucket policy that grants read-only access to everyone.
          Navigate to your S3 bucket in the AWS Management Console.
          Click on the "Permissions" tab.
          Scroll down to the "Bucket policy" section.
          Click on "Edit."
          Paste the bucket policy into the editor and click "Save changes."

     b. IAM Policies :
          If you want more fine-grained control over access, you can use IAM policies.
          To set up an IAM policy in the AWS Management Console for accessing an S3 bucket, follow these steps:
          In the "Find Services" search bar, type "IAM" and select the IAM service.
          In the IAM console, select "Policies" from the left navigation pane.
          Click the "Create policy" button.
          In the "Create Policy" page, choose the service for which you want to create a policy. In this case, choose "S3."
          In the "Actions" section, you can either choose specific actions or select "All S3 actions" for full access. For read-only access, choose actions like "GetObject" 
          and "ListBucket."
          In the "Resources" section, specify the resources to which the policy applies. You can use the bucket ARN (Amazon Resource Name) and object ARN to define the scope.
          Give your policy a name and description.
          Click "Create policy" to save the policy.
          Go to the "Policies" section in IAM.
          Select the policy you just created.
          In the "Policy actions" menu, choose "Attach policy."
          Select the IAM user, group, or role to which you want to attach the policy.

   c. Test Access:
   
          Sign in with the IAM user or assume the role associated with the policy.
          Test access to the S3 bucket based on the permissions granted by the policy.

