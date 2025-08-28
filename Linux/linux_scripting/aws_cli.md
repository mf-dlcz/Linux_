# AWS CLI
List of commands that can be used in the AWS CLI.

<br>

## Command Examples:
- Creates an S3 bucket and specifies bucket name and the AWS Region where it will create the bucket.

```
aws s3api create-bucket --bucket <bucket_name> --region <region>
```

- Use the **aws ec2 run-instance** to launch the instance. Specify the Amazon Machine Image (AMI) ID,
instance type (such as t2.micro), and a key pair to associate it with the instance.
```
aws ec2 run-instance --image-id ami-XXXXXXXXXXXXXXXXX --instance-type t2.micro --key-name my-key-pair
```

- The **aws rds create-db-instance** creates an Amazon RDS instance.
```
aws rds create-db-instance --db-instance-identifier my-db-instance --db-instance-class db.t2.micro --engine mysql --allocated-storage 20 --master-username myuser --master-user-password mypassword
```

- Creates a Lambda function name **my-lambda** function.
```
aws lambda create-function --function-name my-lambda-function --runtime nodejs18.x --role arn:aws:iam::1234567890:role/execution-role --handler index.handler --code file://my-lambda.zip
```