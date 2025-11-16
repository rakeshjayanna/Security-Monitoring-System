AWS Security Monitoring System

This project is a security monitoring setup I created using AWS services.
The main idea is to track activity in AWS Secrets Manager and send an email alert whenever someone accesses or changes a secret.
I set it up for learning and testing purposes. After completing the project, I deleted the AWS resources to avoid charges.



How It Works:

1.Secrets Manager
    =>Stores sensitive data like passwords, tokens, and keys.

2.CloudTrail
    =>Records every action performed in Secrets Manager.
    =>Sends the logs to an S3 bucket and to CloudWatch Logs.

3.CloudWatch Log Group
    =>Receives the CloudTrail logs.
    =>CloudWatch Metric Filter
    =>Checks the logs for specific events such as GetSecretValue, PutSecretValue, UpdateSecret, or DeleteSecret.

4.CloudWatch Alarm
    =>If the filter detects something, the alarm turns on.
    =>SNS (Simple Notification Service)
    =>Sends an email notification to the configured email address.

5.Email
    =>I receive the alert instantly when a secret is accessed or modified.


Why This Is Useful:
    =>Helps monitor secret access.
    =>Detects any unauthorized or unexpected activity.
    =>Sends alerts immediately.
    =>Simple setup for learning or demonstration.


Architecture: 
        →Secrets Manager
        → CloudTrail
        → CloudWatch Logs
        → Metric Filter
        → Alarm
        → SNS
        → Email

CloudTrail also stores logs in an S3 bucket.


What I Did:

    =>Enabled CloudTrail for Secrets Manager.
    =>Set up CloudWatch Logs.
    =>Added a metric filter to detect specific events.
    =>Created a CloudWatch Alarm.
    =>Connected the alarm to SNS for email alerts.
    =>Tested the setup by accessing a secret.
    =>Deleted the resources after testing to avoid billing.
