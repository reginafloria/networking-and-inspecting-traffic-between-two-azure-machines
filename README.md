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
Pinging between vm1 and vm2 through ICMP which is the protocol for pinging showing connectivity.
  
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
<img src="https://imgur.com/oRk6F9l.jpg" height="80%" width="80%" alt="Observing ssh traffic"/>
</p>
<p>
SSH stands for Secure Shell and is used for secure remote login from one virtual machine to another.

Part 2 (Observe SSH Traffic)
  
20. Back in Wireshark, filter for SSH traffic only
21. From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
22. Type commands (ls, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark
23. Exit the SSH connection by typing ‘exit’ and pressing [Enter]

</p>

<img src="https://imgur.com/LMWuS15.jpg" height="80%" width="80%" alt="Topology of the Azure Resources"/>
</p>
<p>
  DHCP (Dynamic Host Configuration Protocol) is a server which manages IP addresses and assigns them to clients.
  
  Part 2 (Observe DHCP Traffic)
  
24. Back in Wireshark, filter for DHCP traffic only
25. From your Windows 10 VM, attempt to issue your VM a new IP address from the command line (ipconfig /renew)
26. Observe the DHCP traffic appearing in WireShark

<img src="https://imgur.com/U5yg8GA.jpg" height="80%" width="80%" alt="Observing ssh traffic"/>
</p>
<p>
  DNS Domain Name System) is like a directory and matches domain names with IP addresses. On the first row it
  matches google.com to an IP address.
  
  Part 2 (Observe DNS Traffic)
  
27. Back in Wireshark, filter for DNS traffic only
28. From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are
29. Observe the DNS traffic being show in WireShark
  
  <img src="https://imgur.com/apAMizX.jpg" height="80%" width="80%" alt="Topology of the Azure Resources"/>
</p>
<p>
  RDP (Remote Desktop Protocol) also known as tcp==3389 is a network communication protocol which allows users to connect
  with another computer from a remote location.
  
  Part 2 (Observe RDP Traffic)
  
30. Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)
31. Oserve the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
32. Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted

  
  


  
  

<p>

  
  














