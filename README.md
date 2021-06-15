Overview

This project covers three tier architecure in AWS, which includes 2 EC2 instance and 1 RDS instance.


Terraform is used to automate the three tier architecture.


Have splitted the terraform codes for each services inorder to have a better visibility.


In this project have used the region us-east-2. I have used the AWS cli to configure the credential on my machine. Instead we can use terraform.tfvars file to parameterize the credential and added to the .gitignorre file when this is commited to the repository.


EC2:
===

Have used the latest AMI of amazon linux AMI from us-east-2 region. The same AMI has been used to create 2 web server instance.


User date:
==========

Have used a simple shell script to install apache on the webservers. We can other use packer to build the AMI.


RDS:
====

mysql RDS instance has been used in this project.


below are the files used in the project.

provider.tf
elb.tf
output.tf
vars.tf
vpc.tf
sg.tf
db.tf
install_apache.sh
terraform.tfstate
instance.tf


And below are the high level explanation of the codes.


vars.tf:

We can parameterize various things on the vars.tf. But for thid project have added a paramter for region alone. usually we can add the parameters for AMI, DB user & passord as well.

provider.tf:

provider.tf files tells us which provider we are going to use. In this project we have used AWS. We can use Azure and other cloud providers as well as Vmware and other onprem platforms as well.

vpc.tf:


In the vpc.tf have created the VPC "Demo VPC" and create seperate subnets for Web, Application and DB. Also created the IG and routes to have the connectivity between eeach layer.


sg.tf

Used sg.tf to create Security groups for each layer.


db.tf

Used to craete a RDS instace and have the paramters for creating the instanse.






