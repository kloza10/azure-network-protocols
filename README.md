<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />





<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create a resource group in Microsoft Azure
- Create Vertuial Machine 1 using Microsoft Windows 10 (12H2) using the previously created resource group
- Create Virtual Machine 2 using Linux (Ubuntu Server 20.04)
- View activity in Network Watcher 
- Connect Virtual Machines to your remote desktop
- Install wireshark
- Begain viewing the traffic 

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/m58NXky.png" 
</p>
<p>
Here we have a our Resource Group created, "RG-Network-Security" we can move on to creating our Virtual Machines.
</p>
<br />

<p>
<img src="https://i.imgur.com/YU7lAOu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here we can see that as we are creating Virtual Machine #1 (VM1) it created its own Virtual Network (Vnet) and Subnet.
</p>
<br />

<p>
<img src="https://i.imgur.com/K8qc3Hh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
While creating Virtual Machine #2 (VM2) we can see here that its on the same network as (VM1).
</p>
<br />
<img src="https://i.imgur.com/i1C0PrV.png" height="80%" width=80%" alt="Disk Sanitization Steps"/>

                                                                                          
We can see here that both Virtual Mschines have been created and we can view them in the Network Watcher in Azure.
                                                                                          

<img src="https://i.imgur.com/36Lk4eJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
                                                                                           
We are now connecting our Virtual Machines to your remote desktop.
                                                                                           

<img src="https://i.imgur.com/sDUgW9a.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
                                                                                           
We have now installed Wireshark, and we will begain to view some traffic.                                                                                           


<img src="https://i.imgur.com/ALkSSAe.png" hight="80%" width="80%" alt="Disk Sanitization Steps"/>

After connecting VM1 and VM2 we are using "icmp" to make sure that everything is connecting well by using "ping" to message VM2 from VM1 and see the cumminication.                                                                                         
                                                                                           

<img src="https://i.imgur.com/cGEoDGj.png" hight="80%" width="80%" alt="Disk Sanitization Steps"/>
                                                                                           
Here we are running a few tests to ensure we have a connection, as you can see after checking the connetion between Virtual Machine #1 and Virtual Machine #2 I
checked to see if I could connect to "www.google.com" I was able to get a response from google, I actually tried google a few times. Furthemore I went into the VM2 to deny "icmp" traffic and as you can see there is a request time out, so I'll go back in to restore it.


<img src="https://i.imgur.com/VqTMRmn.png" hight="80%" width="80%" alt="Disk Sanitization Steps"/>
                                                                                          
So after removing the security rule to deny Icmp ping, we can see that the connection was restored.                                                                                          

<img src="https://i.imgur.com/EbcY4Lr.png" hight="80%" width=80% alt="DIsk Sanitization Steps"/>                                                                                          

 Here we can view the traffic via "SSH"
                                       
                                       
                                       
<img src="https://i.imgur.com/uosWrMj.png" hight="80%" width="80%" alt="Disk Sanitization Steps"/>
                                                                                                
Here we are just some Linux commands just to view the traffic.
                                                                                                
                                                                                                
<img src="https://i.imgur.com/arVJ3ie.png" hight="80%" width="80%" alt="Disk Sanitization Steps"/>
                                                                                                
Here we can see the trffic via "DHCP" we used the ping "ipconfig /renew" to renew an IP address.
                                                                        
                                                                        
 <img src="https://i.imgur.com/CARPpnN.png" hight="80%" width="80%" alt="Disk Sanitization Steps"/>
                                                                                                 
Without using any commands we can see the traffic of communication on "DNS"   
