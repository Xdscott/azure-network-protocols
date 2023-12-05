<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




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

- (Observe ICMP Traffic)
- (Observe SSH Traffic)
- (Observe DHCP Traffic)
- (Observe DNS Traffic)
- (Observe RDP Traffic)



<p>
  
![image](https://github.com/Xdscott/azure-network-protocols/assets/125581739/395ddeec-cb2a-48d2-80ff-2f06f90e21fb)

</p>
<p>
Use Remote Desktop to connect to your Windows 10 Virtual Machine

</p>
<br />

<p>
  
![image](https://github.com/Xdscott/azure-network-protocols/assets/125581739/6ca682c9-ed64-4767-9c51-fe5b0aae5aae)

</p>
<p>
Within your Windows 10 Virtual Machine, Install Wireshark
Open Wireshark and filter for ICMP traffic only
</p>
<br />

<p>
  
![image](https://github.com/Xdscott/azure-network-protocols/assets/125581739/8cb02ff5-5c66-4c3b-b7d7-2b5f87586be5)

</p>
<p>
Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM
Observe ping requests and replies within WireShark

</p>
<br />
<p>
  
![image](https://github.com/Xdscott/azure-network-protocols/assets/125581739/05d85723-bd77-4f50-a88c-f168c4d78214)


</p>
<p>
From The Windows 10 VM, open command line or PowerShell and attempt to ping a public website (such as www.google.com) and observe the traffic in WireShark
</p>
<br />
<p>
  
![image](https://github.com/Xdscott/azure-network-protocols/assets/125581739/4348737d-7415-4053-a5f2-6080e5c693f8)


</p>
<p>
Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM
</p>
<br />
<p>
  


![image](https://github.com/Xdscott/azure-network-protocols/assets/125581739/69171b2c-85c8-4333-a534-f6cc406b1c6e)

<p>
Back in Wireshark, filter for SSH traffic only
From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark
</p>
<br />

<p>
  
![image](https://github.com/Xdscott/azure-network-protocols/assets/125581739/b5e0e543-c984-43bb-8b10-819ff4b28456)

<p>
Back in Wireshark, filter for DHCP traffic only
From your Windows 10 VM, attempt to issue your VM a new IP address from the command line (ipconfig /renew)
Observe the DHCP traffic appearing in WireShark
</p>
<br />

<p>
  
  ![image](https://github.com/Xdscott/azure-network-protocols/assets/125581739/cc2cc3ac-3ccb-4baa-8bfe-f577637df74d)

</p>
<p>
Back in Wireshark, filter for DNS traffic only
From your Windows 10 VM within a command line, use nslookup to see what google.com and disney.com’s IP addresses are
Observe the DNS traffic being show in WireShark

</p>
<br />
<p>
  
  ![image](https://github.com/Xdscott/azure-network-protocols/assets/125581739/94a23ca3-9b0a-4ccf-9864-3eba0765db5b)

</p>
<p>
  Back in Wireshark, filter for RDP traffic only (tcp.port == 3389)
Oserve the immediate non-stop spam of traffic? Why do you think it’s non-stop spamming vs only showing traffic when you do an activity?
Answer: because the RDP (protocol) is constantly showing you a live stream from one computer to another, therefor traffic is always being transmitted

</p>
