# Configure Credentials for AWS CLI
![ScreenShot](https://github.com/NavarroAlexKU/Configure-Credentials-for-the-AWS-CLI/blob/main/Main%20Picture.jpeg)

## Author:
[Alex Navarro]

# Generate User Permissions:
For the AWS account that you want to have access programmatically through the AWS API or the AWS CLI, we need to generate an access key using the "Identity and Access Management (IAM)" service in AWS.
* click Users under the "Access Management" tab on the left of your screen.
* Under the summary tab, select "Security Credentials"
* Scroll down and select "Create access key"
    - NEVER share this information!
    - You can download your credentials to a CSV file if needed.
![ScreenShot](https://github.com/NavarroAlexKU/Configure-Credentials-for-the-AWS-CLI/blob/main/Screenshot%202023-02-14%20at%203.55.41%20PM.png)

## Access Key best practices & alternatives:
* Avoid using long-term credentials like access keys to improve your AWS security. This is a cool feature as you can select what your use case is then IAM will give you suggested alternatives. However, for this specific demonstration we will continue through:
![ScreenShot](https://github.com/NavarroAlexKU/Configure-Credentials-for-the-AWS-CLI/blob/main/Screenshot%202023-02-14%20at%204.15.52%20PM.png)

* For this example we will not set a description tag so you can click next.
* The third page titled "Retrieve Access Keys" will show you the generated Access Key and Secret Access Key
    - I'm not going to show mine for obvious security reasons.

## Configure Credentials on your Operating System:
I'm using a Mac so this specific demonstration will show how to do this on Linux O/S.
* Open your terminal and do the following:
    - type aws configure
    - enter your accesskey then press enter
    - enter your AWS Secret Acess Key and press enter
    - enter your Default region name then press enter
    - enter your output format then press enter

```
$ aws configure
AWS Access Key ID [None]: accesskey
AWS Secret Access Key [None]: secretkey
Default region name [None]: us-west-2
Default output format [None]:
```

## Add permissions to user:
Now that we have our AWS CLI configured for the user, we need to add what permissions we want them to have:
* Go back to AWS IAM
* Click on Users then Permissions tab and select "Add Permissions"

![ScreenShot](https://github.com/NavarroAlexKU/Configure-Credentials-for-the-AWS-CLI/blob/main/Screenshot%202023-02-14%20at%204.35.05%20PM.png)

* I'm going to add full permissions for EC2 and Amazon S3
* Once you've chose the permissions you want for the user, you can click "Add Permissions"

![ScreenShot](https://github.com/NavarroAlexKU/Configure-Credentials-for-the-AWS-CLI/blob/main/Screenshot%202023-02-14%20at%204.38.48%20PM.png)
* For the AWS services you selected for the user to have permissions to, you can run the following command in your terminal:
"aws 'aws service name' ls". So for my example, I gave my user "AmazonS3FullAccess" permissions so my command looks like this:
```
aws s3 ls
```
![ScreenShot](https://github.com/NavarroAlexKU/Configure-Credentials-for-the-AWS-CLI/blob/main/Screenshot%202023-02-14%20at%204.45.50%20PM.png)

