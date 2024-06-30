# 3-Tier-Application-Deploy 
3-TIER ARCHITECTURE IMPLEMENTATION ON EC2 Instance.
Pre-Requertires:
Vpc Name:	3-Tier-Arc-Vpc
Subnet Name:	3-Tier-Arc-Sub-Pvt
Subnet Name:	3-Tier-Arc-Sub-Pub
Instance 1 Name:	3-Tier-Arc-Ec2-Pub-App
Instance 2 Name:	3-Tier-Arc-Ec2-Pvt-DB
Instance 3 Name:	3-Tier-Arc-Ec2-Pvt-Front END
Route Table 1 Name:	3-Tier-Arc-Rt-Pub
Route Table 2 Name:	3-Tier-Arc-Rt-Pvt
Interner Gateway Name:	3-Tier-Arc-Igw
Security Group 1 Pub:	3-Tier-Arc-Sg-FE
Security Group 2 Db:	3-Tier-Arc-Sg-DB
Security Group 3 App:	3-Tier-Arc-Sg-App
Nat Gateway Name:	3-Tier-Arc-NAT

Here is my VPC resource Map

![image](https://github.com/venkey12319/3-Tier-Application-Deploy/assets/167093427/0b03d765-732f-4182-b86b-a317ff550f9b).

Step 2: Establish connection between 3 Secutiy groups

Front End security group:

![image](https://github.com/venkey12319/3-Tier-Application-Deploy/assets/167093427/9c032ae6-31ea-4fcf-8014-fc872617bf77)

Data Base security group:

![image](https://github.com/venkey12319/3-Tier-Application-Deploy/assets/167093427/0bf4d26e-fbd9-4ed9-b88c-8fb0fe4c6a8b)

Application security group:

![image](https://github.com/venkey12319/3-Tier-Application-Deploy/assets/167093427/61937e1e-5e57-4be0-ad8b-7b913ba27878)




