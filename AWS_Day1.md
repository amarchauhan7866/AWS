# AWS


Task 1
Create a vpc through wizard, having one public subnet and one private subnet.

Solution: 
      Created VPC through vpc wizard of 10.0.0.0/16 CIDR in N.California region.

![VPCcreate_Wizard1](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day1/VPCcreate_Wizard1.PNG)

############################################

Create Public & Private Subnet

![VPC_Subnet2](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day1/VPC_Subnet2.PNG)


#####################################################

Task 2
Create two instances within the vpc that you created in task 1, windows instance in public subnet and linux instance in private subnet. check if linux is pingable from windows and vice versa.

Solution: 
 Created windows EC2 instance in public Subnet:
 
 ![Windows](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day1/Windows%20Configuration_1.PNG)
 
 Created Linux EC2 instance in private Subnet:
 
 ![LinuxWindows](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day1/VPC_Installation_.PNG)
 
 Task 3
Delete all the instances and now make those two instances that you created in previous task using aws-cli.

Deleted all the INstances which is created by GP wizard

Fristly i have installed the AWS CLI

yum install awscli

[root@amar ~]#  aws --version
aws-cli/1.14.28 Python/2.7.5 Linux/3.10.0-862.2.3.el7.x86_64 botocore/1.8.35

Configured the ASWaccess key and AWSSecretKey under the directory

vim  ~/.aws/config

and set the accesskey path under the .bashrc dircetory 
vim ~/.bashrc

export AWS_CONFIG_FILE=$HOME/.aws/config

###################################################
Aws configure using cli

Created Key Pair & Save the key in local system

 aws ec2 create-key-pair --key-name devenv-key --query 'KeyMaterial' --output text > devenv-key.pem

Created the Security Group

 aws ec2 create-security-group --group-name devqa-sg --vpc-id vpc-c90b47ae --description "security group for development environment"
 
 
 ##########################################################
Now Created Windows EC2 Instance in public subnet

aws ec2 run-instances --image-id ami-b236d2d1 --count 1 --instance-type t2.micro --key-name devenv-key --security-group-ids sg-0e88ec56cbeb836d1 --subnet-id subnet-05b67bcb0607a61f1

Now Created Linux EC2 Instance in private subnet

aws ec2 run-instances --image-id ami-0e86606d --count 1 --instance-type t2.micro --key-name devenv-key --security-group-ids sg-0e88ec56cbeb836d1 --subnet-id subnet-0134aa7f4ad5299a9

![CLIoutput](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day1/CLI%20Mode%20Create%20Vm.PNG)

 
