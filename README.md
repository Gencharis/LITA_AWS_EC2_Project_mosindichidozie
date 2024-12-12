# LITA_AWS_EC2_Project_mosindichidozie
 Setting up VPC, configuring and launching EC2 intances with Apache webserver deployed on it.
 
## VPCs Creation
 VPC(vpc-old90a2e99515012a(lita_project-vpc)) and subnet was officially created for us by our project surpervisor, to accomodate our AWS environment.
 The VPC has a CIDR of 10.0.0.0/16.
 
## Creation of security group 
 To get to the security group we searched out EC2 on the search column of our landing page after sigin, the security group is the first on the left partitioning of the page under the NETWORK & SECURITY drop down.
 i created my security group  with my name inconjunction with the naming convention given to us by our surpervisor, and used a DESCRIPTION; allowing SSH and HTTP traffic and used the VPc provided us already as instructed.
 ![security group](/SG_naming.png)
 ![security group](/creating_security-group.png)
 
### INBOUND RULES
in creating security groups adding rules are very necessary to help control traffic flow and security. In my project i allowed for TYPE;SSH,HTTP traffic and SOURCE;anywhere-IPv4, making it easily accesible to mobile user.
![inbound RULES](/inbound_sg.png)

### OUTBOUND RULES
Configured to allow all traffick flowout, which is the default settings.
![OUTBOUND](/Outbound_SG.png)
![OUTBOUND](/SG_created.png)
 
## LAUNCHING OF EC2 INSTANCES
After the configuring and creation of my security group,it was time to launch my instances. Instances is also situated on the left hand of the EC2 page,i clicked the launch instances button, then named my instances with naming convention as instructed by my supervisor,
![LAUNCHING EC2](/instances_config.png)
configure it to work with the AMAZON LINUX2 AMI which has a free tier eligibility,instance type, was left to default t2.micro,
![LAUNCHING EC2](/instances_type.png)
![LAUNCHING EC2](/instance_config.png)
created a keypair and selected it to aide connection to my instance. edited the network settings to carry the official VPC and subnet public created for us, for easy access via internet,
![LAUNCHING EC2](/instances_keypair.png)
also enable auto-assign publicIp so as to allow the instance allocate a random ip to it. filled in the already created security Group,left the storage capacityn to default also.
![LAUNCHING EC2](/instances_confSG.png)
after all the configuration i launched my instance and refreshed for it to show in the list columns of instances, waited for initialization to be completed to the get the '2/2 checked passed' in the status column.
![LAUNCHING EC2](/inst_launchin.png)
![LAUNCHING EC2](/inst_lauched.png)

## CONNECTION OF INSTANCES TO LAUNCH APACHE WEBSERVER
After the succesful launching of my instances i connected to the instances through the connection button, copied the command on my ssh client to ensure my key is not publicly viewable and ran it on my system terminal(opening my terminal on the download folder which has the file of my keypair),then also copied the example that has my keypair,which i succesfully connected
![CONNECTION](/status_chk.png)
![CONNECTION](/inst_terminal.png)
After that i ran the set of command provided for us through the project file to install and enable Apachewebser
![CONNECTION](/apache_instal.png)
which i was successful and confirmed by using the public address orvide in myconsole under security and launched it on my browser,
![CONNECTION](/Apache.png)

## TERMINATING MY instance
After the successful installation,launch and physical confirmation of the Apachewebserver, i terminated my instances by clicking on instances state dropdown button and choosing the TERMINATE INSTANCE option.
![TERMINATING](/inst_termin.png)