### AWS SDK for Python (Boto3) to interact with AWS services programmatically.
```
  pip install boto3
```
install AWS CLI on linux and set AWS credentials using the aws configure command
```
  curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
  unzip awscliv2.zip
  sudo ./aws/install
```
### Services
- **S3**
  connecting via python package
```
import boto3

# Replace 'your-bucket-name' with your desired bucket name
bucket_name = 'your-bucket-name'

s3 = boto3.client('s3', aws_access_key_id=ACCESS_KEY,
                      aws_secret_access_key=SECRET_KEY)  # if aws credentials not configured on aws cli


s3 = boto3.client('s3')
s3.create_bucket(Bucket=bucket_name)
#uploading file
s3.upload_file(local_file_name, bucket_name, s3_file_name)
#checking
objects = s3.list_objects(Bucket=bucket_name)

#retreiving data
# List S3 buckets
response = s3.list_buckets()
for bucket in response['Buckets']:
    print(f'Bucket Name: {bucket["Name"]}')
```
- **RDS**
```
import boto3

# Create an RDS client
rds = boto3.client('rds', region_name='us-east-1')

# List RDS DB instances
db_instances = rds.describe_db_instances()
for db_instance in db_instances['DBInstances']:
    print(f'DB Instance ID: {db_instance["DBInstanceIdentifier"]}')
  
```





