<h1>Multi-VPC Account Architecture Lab</h1>


<h2>Description</h2>
In this project I created three VPCs with private subnets. Each VPC has subnets in two Availability Zones (AZs) within the Region. I deployed one EC2 instance per VPC to demonstrate that, by default, VPCs provide network isolation. Created a VPC Peering Connection, which is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Ultimately establishing VPC point-to-point peering links between each VPC that was created. Next I took a more scalable approach and utilized the AWS Transit Gateway (TGW). I removed the point-to-point peering connections between the VPCs that we established earlier, and setup a Transit Gateway (TGW) to interconnect all three of the VPCs.
<br />


<h2>Applications and Services Used</h2>

- <b>VPC</b> 
- <b>EC2</b>
- <b>IAM</b> 

<h2>Environments Used </h2>

- <b>AWS Linux</b> 

<h2>Lab Walk-through:</h2> 

<p align="center">
Lab 1.1 Create Three VPCs: <br/>
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/515dc8c0-3160-4bd5-a4d5-f518da622f35" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<p align="center">
Step 1: Navigate to VPC Dashboard Services <br/>
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/9d184a70-4c94-4a9f-86cb-0cb2b93902a5" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<p align="center">
Step 2: Navigate to your VPCs and click "Create VPCs" <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/e5dd7f65-04f1-4e4f-95be-e483a83d5bfc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<p align="center">
Step 3: Choose settings and click Creat VPC <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/1f5aeb62-cff3-4e24-b79e-3792c70fac54" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<p align="center">
Step 4: Repeat the first three steps to create VPC B and VPC C.  <br/>  

<p align="center">
After completing these steps, you should have three new VPCs and default listed under "Your VPCs:"   <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/f0da0175-678e-4688-bd52-4dc01ff47e62" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<p align="center">
1.2 Create Subnets: Ceate two subnets for each VPC, one per availability zone (AZ). <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/61b6a580-3b22-45e8-a8d4-e42c9e51fc35" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<p align="center">
Step 1: Navigate to Subnets pannel <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/5113df4d-cf74-4b3f-9139-333253c5826a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

  <p align="center">
Step 2: Click on create subnet and choose VPC <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/c4096bf0-d89d-4ad8-84c9-7cc9ea028855" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

 <p align="center">
Step 3: Create subnets with names that reflect VPC and AZ placement such as VPC A - AZ1, select AZ and provide subnet CIDR  <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/22cc18f6-09a9-4dc3-b286-a3ab96c74344" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

 <p align="center">
Step 4: Click on Add new subnet to add one more subnet into AZ2 with name like VPC A - AZ2 <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/1c0fb269-900a-49b8-8d86-c6716cc4f1c2" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

<p align="center">
Step 5: Repeat the steps above to create subnets for VPC B and VPC C <br/>

 <p align="center">
After you finish these steps, six new subnets should be available <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/31170a09-324e-402f-bfac-3c8710c9d02c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

 <p align="center">
1.3 Deploy Internet Gateways <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/756d6bfc-33ce-4624-8342-cd0bf59556c3" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

 <p align="center">
Step 1: Navigate to Internet Gateways (IGW) and click create internet gateway <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/1685f6e5-446c-4f57-9020-9af481bc2366" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

 <p align="center">
Step 2: Give it a name such as VPC A - IGW. Click "Create internet gateway" <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/31268fea-b7f9-42ce-88b4-afcfc8e116ce" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 

 <p align="center">
Step 3: Select newly created IGW and click on "Attach to VPC" <br/> 
<img src="https://github.com/brycehallcloud/Multi-VPC-Account-Architecture/assets/144934324/10fb13d6-a81a-4751-a7d6-df8ca6ff30c1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
... (308 lines left)
