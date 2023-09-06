# Cloud
### Providers
1. AWS
2. Azure
3. GCP

### AWS EC2 Instance -- Virtual system
*Free Tier Configs*

- Amazon Linux 2023 AMI
- t2.micro -1 GB
- 8 - 32 GB storage

#### Process
AWS Account >> Launch Instances >>> Linux >>> Create security key and it downloads  xxx.pem automatically for SSH connect
change key Permission

```
{
  chmod 400 xxx.pem    ## changing security key file permission
  ssh -add "xxx.pem"  ## adding to local machine
  ssh -i xxx.pem ec2-user@public-ip
}
```

#### initial setups
```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
### AWS RDS Instance -- Relational database



Useful Links
https://www.knowledgehut.com/tutorials/aws
