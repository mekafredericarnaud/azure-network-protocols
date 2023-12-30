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

<h2>Actions and Observations</h2>

- CREATE OUR RESOURCES
</p>
1. Create Two Virtual Machine within the same Resource Group (RG-lab).  
<img src="https://i.imgur.com/Ggj0Tjw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
     a. Windows 10 Virtual Machine (VM1).
<img src="https://i.imgur.com/EU0Z4O5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
     b. Linux (Ubuntu) Virtual Machine (VM2).
<img src="https://i.imgur.com/HIHuJei.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
- OBSERVE ICMP TRAFFIC
</p>
2. Use Remote Desktop to connect to your Windows 10 Virtual Machine (VM1).
<img src="https://i.imgur.com/pSzySuB.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
3. Download and Install Wireshark within your Windows 10 Virtual Machine (VM1).
<img src="https://i.imgur.com/pdfHHhw.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/FWev1dQ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
4. Open Wireshark and filter for ICMP traffic only.
</p>
a. Open Wireshark.
<img src="https://i.imgur.com/PcoZbF3.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/e6KyYEM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ZMX0Yhe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
b. Filter ICMP.
<img src="https://i.imgur.com/bmqTBjI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
5. Open command line or Powershell and attempt to ping the private IP address (10.0.0.5) of the Ubuntu Virtual Machine.
<img src="https://i.imgur.com/JSrpANx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
a. Observe ping request and replies within Wireshark.
<img src="https://i.imgur.com/V5A60gO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
6. Ping a public 

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
