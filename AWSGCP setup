---
id: pubcloudaccsetup
title: Public Cloud Service Account Setup
sidebar_label: Public Cloud Service Account Setup
---

To be able to access a user public cloud account, create a programmatic access user account on the cloud account with a given set of permissions that allows creation, deployment, and management the cloud account. These are the requirements for the user account credential to operate the Lyrid platform.

## Amazon Web Services Credential Role Requirements
To be able to use AWS Account, we require the user to create a default policy. This default policy will be used by the service account that will execute the Lyrid operations. Follow the step by step instructions below to complete this requirement:

### Step 1: Open your AWS IAM Console
Log into AWS with your AWS user credential, and go to this URL to manage IAM user:
**https://console.aws.amazon.com/iam/home**

### Step 2: Create a Policy
Click on "Policies" on the left tab and then click on "Create policy".

![](/img/a2.png)
 
To be able to utilize all Lyrid functionality, create the default policy by importing the JSON below: 
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "logs:GetLogRecord",
                "lambda:GetAccountSettings",
                "lambda:CreateEventSourceMapping",
                "logs:GetLogDelivery",
                "logs:ListLogDeliveries",
                "logs:DeleteResourcePolicy",
                "logs:CancelExportTask",
                "logs:DeleteLogDelivery",
                "lambda:ListLayerVersions",
                "lambda:ListLayers",
                "s3:HeadBucket",
                "logs:PutDestination",
                "logs:DescribeResourcePolicies",
                "logs:DescribeDestinations",
                "logs:DescribeQueries",
                "lambda:ListFunctions",
                "logs:PutDestinationPolicy",
                "s3:ListJobs",
                "logs:StopQuery",
                "logs:TestMetricFilter",
                "logs:DeleteDestination",
                "logs:CreateLogGroup",
                "logs:CreateLogDelivery",
                "logs:PutResourcePolicy",
                "logs:DescribeExportTasks",
                "s3:ListAllMyBuckets",
                "logs:GetQueryResults",
                "logs:UpdateLogDelivery",
                "lambda:ListEventSourceMappings",
                "s3:CreateJob"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "iam:CreatePolicy",
                "iam:GetRole",
                "iam:PassRole",
                "iam:DetachRolePolicy",
                "iam:GetPolicy",
                "iam:ListAttachedRolePolicies",
                "iam:DeletePolicy",
                "iam:CreateRole",
                "iam:DeleteRole",
                "iam:AttachRolePolicy"
            ],
            "Resource": [
                "arn:aws:iam::*:policy/service-role/LyridAWSLambda*",
                "arn:aws:iam::*:role/service-role/lyrid*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:*:*:job/*",
                "arn:aws:s3:::*/*",
                "arn:aws:s3:::lyrid*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": "lambda:*",
            "Resource": "arn:aws:lambda:*:*:layer:*"
        },
        {
            "Effect": "Allow",
            "Action": "logs:*",
            "Resource": "arn:aws:logs:*:*:log-group:lyrid*:log-stream:lyrid*"
        },
        {
            "Effect": "Allow",
            "Action": "lambda:*",
            "Resource": [
                "arn:aws:lambda:*:*:event-source-mapping:*",
                "arn:aws:lambda:*:*:layer:*:*",
                "arn:aws:lambda:*:*:function:lyrid*"
            ]
        },
        {
            "Effect": "Allow",
            "Action": "logs:*",
            "Resource": "arn:aws:logs:*:*:log-group:lyrid*"
        }
    ]
}
```

Name the policy "LyridDefaultPolicy", and click "Create policy":

![](/img/a2-2.png)

### Step 3: Create a service account.
Click on "Users" on the left tab and then click the "Add user" button:

![](/img/a3.png)

Set the username, and select programmatic access. Then, click "Next":

![](/img/a33.png)

On the next page, select "Attach existing policies directly", filter by the word Lyrid, attach the policy that you
created on the Step #2, and click "Next".

![](/img/a333.png)

(Optional) Add tags if as you need, verify the permissions, and create user:

![](/img/a3333.png)

Input the Access Key ID and Secret Access Key. This will be used by Lyrid CLI client to submit AWS credential into the
Lyrid platform:

![](/img/a33333.png)

---

## Google Cloud Platform Credential Role Requirements

### Step 1: Create a service account
Log into Google Cloud Platform console at:
**https://console.cloud.google.com/**

:::info
Verify that you are selecting the correct project.
:::

Navigate to the "IAM & admin" and click on "IAM":

![](/img/g1.png)

Click on "Service Account" in the left tab:

![](/img/g11.png)

![](/img/g111.png)

### Step 2: Attach Permission to Service Account
Add these following permissions into the service account:

![](/img/g2.png)
:::info Role Description
- **Service Account User** : To run GCP operations as service account
- **Logging Admin** : The create/read serverless endpoints logs
- **Cloud Run Admin** : To create/delete/update serverless endpoints
- **Storage Admin** : To view, list, and push and delete container images
:::

### Step 3: Create JSON Credential File
Select "Create Key" for that service account on the last step of creation:

![](/img/g3.png)

Choose JSON format, and save the JSON file to be used by Lyrid CLI to submit the GCP credential into the Lyrid platform:

![](/img/g33.png)

### Step 4: Enable Cloud Resource Manager API

Copy this URL, replace `<project-id>` with the Google Project ID, then follow the following step:
```bash
https://console.developers.google.com/apis/api/cloudresourcemanager.googleapis.com/overview?project=<project-id>
```

Click on the ENABLE API:

![](/img/g4.png)

### Step 5: Enable Cloud Run API

Copy this URL, replace `<project-id>` with the Google Project ID, then follow the following step:
```bash
https://console.developers.google.com/apis/library/run.googleapis.com?project=<project-id>
```

Click on the ENABLE API:

![](/img/g5.jpg)

---

## Linking Cloud Service account to Lyrid Platform
Now that you've finished setting up your Public Cloud Service Account, The next step would be linking your account to Lyrid Platform.

[***Managing Cloud Credentials***](connectpubcloud.md)

### Step 6: Enable Cloud Run API

Copy this URL, replace `<project-id>` with the Google Project ID, then follow the following step:
```bash
https://console.developers.google.com/apis/library/run.googleapis.com?project=<project-id>
```

Click on the ENABLE API:

![](/img/g5.jpg)

---

## Linking Cloud Service account to Lyrid Platform
Now that you've finished setting up your Public Cloud Service Account, The next step would be linking your account to Lyrid Platform.

[***Managing Cloud Credentials***](connectpubcloud.md)
