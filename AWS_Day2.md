Solutions AWS_Assignment_Day2

Created a VPC manually :-
Click on Your's VPC
Click on Create New VPC

![AmarVPC](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day2/VPC.PNG)

Created 2 Public Subnets, 2 Private Subnets and 2 Protected Subnets.

![Subnet](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day2/Subnet.PNG)

Created all the required route table
Created Route tables and assigned to each Subnet
Public Route Table attached to both Public Subnets
Private Route Table are being created for each Private Subnet

Note:- Under the Public Route Table i have attahced the igw and for private subnet i have attached the NAT gateway


![RouteTable](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day2/RouteTable.PNG)

Created a IGW and assigned it to newly created VPC:-

![IGW](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day2/InternetGateway.PNG)

Now Created the NAT Gateway:

![NAT](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day2/NATGateway.PNG)

Now Launch 2 the new instance echa private subnet 
and also lauch a instance in public subnet

![Instance](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day2/Instance.PNG)

########################################################################

Now create the LB and add the both instance under the newly created LB

Now checked the both the instance on the web
Server:-1
![Webpage](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day2/WebPageServer-1.PNG)

Server:-2

![Webpage2](https://github.com/amarchauhan7866/AWS/blob/master/AWS/Media/Day2/WebPageServer-2.PNG)


