# 3-Tier-Application-Deploy 
3-TIER ARCHITECTURE IMPLEMENTATION ON EC2 Instance.

Pre-Requertires:

1) Vpc Name:  3-Tier-Arc-Vpc
2) Subnet 1 Name: 3-Tier-Arc-Sub-Pvt
3) Subnet 2 Name: 3-Tier-Arc-Sub-Pub
4) Instance 1 Name: 3-Tier-Arc-Ec2-Pub-App
5) Instance 2 Name: 3-Tier-Arc-Ec2-Pvt-DB
6) Instance 3 Name: 3-Tier-Arc-Ec2-Pvt-Front End
7) Route Table 1 Name: 3-Tier-Arc-Rt-Pub
8) Route Table 2 Name: 3-Tier-Arc-Rt-Pvt
9) Internet Gateway Name: 3-Tier-Arc-Igw
10) Security Group 1 Pub: 3-Tier-Arc-Sg-FE
11) Security Group 2 Db: 3-Tier-Arc-Sg-DB
12) Security Group 3 App: 3-Tier-Arc-Sg-App
13) Nat Gateway Name: 3-Tier-Arc-NAT

Here is my VPC resource Map

![image](https://github.com/venkey12319/3-Tier-Application-Deploy/assets/167093427/0b03d765-732f-4182-b86b-a317ff550f9b).

Step 2: Establish a connection between 3 Security groups

Front End security group:

![image](https://github.com/venkey12319/3-Tier-Application-Deploy/assets/167093427/9c032ae6-31ea-4fcf-8014-fc872617bf77)

Data Base security group:

![image](https://github.com/venkey12319/3-Tier-Application-Deploy/assets/167093427/0bf4d26e-fbd9-4ed9-b88c-8fb0fe4c6a8b)

Application security group:

![image](https://github.com/venkey12319/3-Tier-Application-Deploy/assets/167093427/61937e1e-5e57-4be0-ad8b-7b913ba27878)

Step 3: Install the webserver in the FE instance

log in to Mobaxterm with the public IP address of that instance.

Commands to run:

Sudo apt update (because we are using UBUNTU Machine image)

sudo apt install nginx (To install)

sudo systemctl status nginx (To verify installation)

Step 4: Create key to connect private virtual machines

Commands to run:

vim venkat_key.pem

Copy the pem file from your local server and save it

chmod 400 venkat_key.pem (To give permissions)

Step 5: Connect to the DB instance and install the MYSQL server

ssh -i venkat_key.pem ubuntu@10.0.06 (i provided ec2 instance private iD)

Commands to install and create an account:

sudo apt update

sudo apt install mysql-server (To Install MySql)

sudo systemctl status MySQL   ( To Check the Active Status of MySql)

sudo MySQL ( To log in mysql server as a root)

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'admin@123456!'; ( To create account with credentials)

FLUSH PRIVILEGES;  (To flush privileges)

Step 6: To provide some data to verify

Test the MySql server if it is working by running sample sql queries

Follow the below Commands

CREATE DATABASE mysql_test;

USE mysql_test;

CREATE TABLE table1 (id INT, name VARCHAR(45));

INSERT INTO table1 VALUES(1, 'Virat'), (2, 'Sachin'), (3, 'Dhoni'), (4, 'ABD');

SELECT * FROM table1;

creation of MySQL server is successful. 


















