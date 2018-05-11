+++
title ="Serverless IAM Permissions"
description = "Minimal Serverless Permissions"
date = 2018-02-01T10:01:57-05:00
tags = ["AWS"]
+++

How do we create an IAM (Identity Access Management) user with the bare minimum permissions to access the resources it needs for Serverless? What do the individual IAM services and permissions mean? 

## Intro


In the wonderful world of Amazon lambda, you write the function code and execute it on Amazon's infrastructure. But outside of just Amazon Lambda there are multiple other Amazon resources your Lambda taps into including API Gateway, Cloudformation and more depending on what you're doing. To tap into these different services programmatically, you can setup and configure a tool like the `awscli` and create a user on Amazon IAM through the admin interface. When you create the user, you can grant it programmatic access.


With a tool like Serverless, it utilizes the AWS APIs to programmatically manage Amazon resources on your behalf. But all these methods relinquish control of your resources to a 3rd party. 

You can use `AdministratorAccess` to give a whitelist for your user to do everything  but it makes your system accessible to everyone. Whether the script is then able to touch resources its not suppose to or the user role is compromised and you've now opened up more of your system. 

It's nice to give it just the permission it needs but let's understand the services and the permissions they use. 



## Permissions

With all IAM roles, there are policies. Amazon provides a few IAM role templates they manage for common policies; Users are also allowed to customize and define their own User policies.

### Lambda

 To run your lambdas of course you need some IAM Lambda* Access. 
Amazon provides some broad templates like `AWSLambdaFullAccess` which give access to all services Lambda can hit (S3, Dynamo, Kinesis). But the permission can be as fine grain as  `AWSLambdaExecute` which only gives it access to send requests to CloudWatch. 

 ### API Gateway

 If you want to hit your lambda from the public internet, you will need an API Gateway. This gives Amazon a place to redirect your requests to specific lambdas and URL mapping. Typically `AWSStorageGatewayFullAccess` is used to manage endpoints by serverless.

 ### Cloudformation

 Cloudformation templates are templates to create infrastructure on Amazon. They're YAML based but very powerful and flexible. Serverless uses this in the background to manage other services also. Amazon doesn't provide except a read-only template `AWSCloudFormationReadOnlyAccess` as of now. You will have to define a custom definition if you want to give serverless access to cloudformation.


A policy discussed here, you can define as JSON version templates will allow serverless to create and build Stacks as it needs. When you define a new policy give it a relevant name such as `CloudFormationFullAccess` and tag it with the below JSON policy.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1449904348000",
            "Effect": "Allow",
            "Action": [
                "cloudformation:CreateStack",
                "cloudformation:CreateChangeSet",
                "cloudformation:ListStacks",
                "cloudformation:UpdateStack",
                "cloudformation:DeleteStack",
                "cloudformation:Describe*",
                "cloudformation:ExecuteChangeSet",
                "cloudformation:ValidateTemplate"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
}
```

### Other Permissions

Other permissions can be done on a case by case basis. I wanted to under the hood the minimum number of resources you needed to interact with Serverless through terraform [here](https://github.com/tealtail/wildryde-terraform-serverless).

Being its an uncommon ask there were already questions about this on the github serverless forum. This user here [berry2012 generated a full list](https://github.com/serverless/serverless/issues/588) from their finding that I found super helpful also to further my understanding. 
