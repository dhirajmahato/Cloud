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
  chmod 400 xxx.pem    # changing security key file permission
  ssh -add "xxx.pem"   # adding to local machine
```
For Secure Connection to Remotr Host
```
  ssh -i xxx.pem ec2-user@public-ip
```
For Secure File transfer
```
  scp -i /directory/to/abc.pem /your/local/file/to/copy ec2-user@public-ip:path/to/file
```

#### initial setups
```
  sudo dnf update -y
```
```
  sudo dnf install git -y  // for git version control  
```
For DB Servers
```
  sudo dnf install mariadb105-server  # for SQL **database server**
  sudo systemctl start mariadb //Starts MariaDB service
  sudo systemctl enable mariadb //Enabled MariaDB service to restart on reboot
```
For Web Servers 
```
  sudo dnf install -y nginx  // for **web server**
  sudo systemctl start nginx.service
  sudo systemctl enable nginx.service 
```
For kafka Servers 
```
  sudo yum install java-1.8.0
  java -version

  wget https://dlcdn.apache.org/kafka/3.5.0/kafka_2.13-3.5.0.tgz
  tar -xzf kafka_2.13-3.5.0.tgz
  bin/zookeeper-server-start.sh config/zookeeper.properties  ## zookeper
  export KAFKA_HEAP_OPTS="-Xmx256M -Xms128M"
  cd kafka_2.13-3.5.0
  bin/kafka-server-start.sh config/server.properties    ##kafka server

```
### AWS RDS Instance -- Relational database

- After creating RDS instance with **same VPC (Virtual Private cloud)** as of EC2 instance 
- Having *security group* **inbound rules** as custom on port 3306 for mysql connecting from anywhere.
```
  mysql -h <endpoint address> -P 3306 -u admin -p
```
Useful Links
- https://cloudkatha.com/how-to-install-mariadb-on-amazon-linux-2023/
- https://www.knowledgehut.com/tutorials/aws and [youtube](https://youtu.be/qdk1p1zgBPI)
