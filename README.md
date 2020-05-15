## Summary
Amazon CloudWatch Events trigger this check when AWS CloudTrail logs EC2 API calls. Specifically, Amazon CloudWatch Events Rules monitoring AWS CloudTrail Logs, trigger based on an API call for "EC2 Instance State-change Notification". The trigger invokes AWS Lambda. The Lambda function will send an SNS notification and use SSM to install AWS Inspector agent.

## Deployment

To deploy this security control, upload the security control Lambda ZIP file to a location in Amazon S3. This location must be in the same region you intend to deploy the control.

Launch the provided AWS CloudFormation template using the AWS Console and provide the following information:

  | Parameter            | Description
  | -------------------- | --------------------------------------------------------------------------------------------------
  | S3 Bucket            | The S3 bucket name you uploaded the Lambda ZIP to
  | S3 Key               | The S3 location of the Lambda ZIP. No leading slashes. (ex. Lambda.zip or controls/lambda.zip. )
  | Notification Email   | An email address where you would like violation notifications sent

