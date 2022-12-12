<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create our Resources
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic
- Lab Cleanup (DON’T FORGET THIS)

<h2>Actions and Observations</h2>

<p>
<img src="https://imgur.com/V2DGxdJ.jpg" height="80%" width="80%" alt="Topology of the Azure Resources"/>
</p>
<p>
Display of two virtual machines, vm1 and vm2.  Two network security groups, two NIC cards (software) for each virtual machine,
two IP addresses, one default gateway, and one virtual network.
  
Part 1 (Create our Resources)
  
1. Create a Resource Group
2. Create a Windows 10 Virtual Machine (VM)
3. While creating the VM, select the previously created Resource Group
4. While creating the VM, allow it to create a new Virtual Network (Vnet) and Subnet
5. Create a Linux (Ubuntu) VM
6. While create the VM, select the previously created Resource Group and Vnet
7. Observe Your Virtual Network within Network Watcher

</p>
<br />

<p>
<img src="https://imgur.com/4fP5DNV.jpg" height="80%" width="80%" alt="Pinging between vm1 and vm2"/>
</p>
<p>
Pinging between vm1 and vm2 through ICMP which is the command for pinging.
  
- For example the source IP address on row 1 is 10.0.0.4 and the destination IP address is 10.0.0.5. 
  
Part 2 (Observe ICMP Traffic)
  
8. Use Remote Desktop to connect to your Windows 10 Virtual Machine
9. Within your Windows 10 Virtual Machine, Install Wireshark
10. Open Wireshark and filter for ICMP traffic only
11. Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM
12. Observe ping requests and replies within WireShark
13. From The Windows 10 VM, open command line or PowerShell and attempt to ping a public website (such as www.google.com) and observe the traffic in WireShark
14. Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM
15. Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic
16. Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity
17. Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is using
18. Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working)
19. Stop the ping activity

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
