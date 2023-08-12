# gpc-vpc-peering
In Google Cloud Console > VPC Network > VPC Networks > Create VPC Network 

created vpc1  with in us-central1  region and subnet 192.168.0.0/24

created vpc2 in us-west1  region and subnet under subnet 10.10.0.0/24

Firewall Rules
As we are testing mode, so we allowed all ICMP, SSH and Custom ingress in both of the VPC

<img src="https://cdn-images-1.medium.com/v2/resize:fit:1600/1*X8MOvRZGTcZ7f0gi6z2Neg.png"/>

Creating VM’s,  vm1 and vm2 under vpc1 and vpc2 

In Google Cloud Console >  VM Instances > Create Instance 

Under VPC1, created VM1  in us-central-1  with internal ip 192.168.0.4
in the same way
Under VPC2 created VM2  in us-west1-b with internal ip 10.10.0.3

<img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*TeLf9_v7g6mB2VAVNYckGQ.png"/>

VPC Peering

So, after creating the VM’s  we need to peer those 2 VPC  so that  both VMs in those VPC
can communicate through private IP

From Google Cloud Console > VPC Network > VPC Network peering

it will be 2 way peering

First  peering will be VPC1 to VPC2
Second peering will be from VPC2 to VPC1
<img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*BnyTm7LiVxS7_jcW2aFFfQ.png"/>
 
after VPC peering done  go to 
Google Cloud Console > Compute Engine > VM Instances 

From the SSH, login to the console of VM1  and ping to 10.10.0.3
in the same way  using SSH login to the console of VM2 and ping to the  VM1’s IP 192.168.0.4

in both scenerio you will see that pings are working

