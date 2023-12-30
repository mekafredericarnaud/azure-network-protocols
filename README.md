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
1. Create a Resource Group (RG-lab) with Virtual Machine.  
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
5. Open command line or Powershell and attempt to ping the private IP address (10.0.0.5) of the Linux (Ubuntu) Virtual Machine (VM2).
<img src="https://i.imgur.com/JSrpANx.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
a. Observe ping request and replies within Wireshark.
<img src="https://i.imgur.com/V5A60gO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
6. On the command line or Powershell, attempt to ping a public website (such as www.google.com) and observe the traffic in Wireshark.
<img src="https://i.imgur.com/nc8VjtO.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ZnTbWPV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
7. Initiate a perpetual/non-stop ping from Windows 10 Virtual Machine (VM1) to Linux (Ubuntu) Virtual Machine (VM2) on the command line or Powershell.
<img src="https://i.imgur.com/8So7mgL.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/nWphlWK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
a. Open the Network Security Group in the Linux (Ubuntu) Virtual Machine (VM2) and disable incoming (inbound) ICMP traffic.
<img src="https://i.imgur.com/JnaataW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/TQewARH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
b. Back in the Windows 10 Virtual Machine (VM1), observe the ICMP traffic in Wireshark and the command line Ping activity.
<img src="https://i.imgur.com/TKhnZQy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/4ur53iV.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
c. Re-enable ICMP traffic for the Network Security Group in the Linux (Ubuntu) Virtual Machine (VM2). 
<img src="https://i.imgur.com/qHvulmL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/09FPvDF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
d. Back in the Windows 10 Virtual Machine (VM1), observe the ICMP traffic in Wireshark and the command line Ping activity (should start working).
<img src="https://i.imgur.com/KGgbKB3.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/AHScBgS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
e. Stop the Ping activity with the command (Ctrl+C).
</p>
<br />
- OBSERVE SSH TRAFFIC
</p>
8. Back in Wireshark, filter for SSH traffic only
<img src="https://i.imgur.com/CcAzXaH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
9. From the Windows 10 Virtual Machine (VM1), "SSH into" the Linux (Ubuntu) Virtual Machine (via its private IP address 10.0.0.5).
</p>
a. 
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
b.
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
- OBSERVE DHCP TRAFFIC
</p>
10. Back in Wireshark, filter for DHCP traffic only.
<img src="https://i.imgur.com/SkF16Js.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
11. From the Windows 10 Virtual Machime (VM1), attempt to issue a new IP address from the commend line (ipconfig/renew).
<img src="https://i.imgur.com/SvQHi5h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
a. Observe the DHCP traffic appearing show in Wireshark.
<img src="https://i.imgur.com/aiQj14f.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
- OBSERVE DNS TRAFFIC
</p>
12. Back in Wireshark, filter for DNS traffic only.
<img src="https://i.imgur.com/gkFmw8N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
13. From your Windows 10 Virtual Machine (VM1) within a command line, use nslookup to see what google.com's IP address is:
<img src="https://i.imgur.com/jQOMdFx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
a. Observe the DNS traffic being show in Wireshark.
<img src="https://i.imgur.com/bcq2WyD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
- OBSERVE RDP TRAFFIC
</p>
14. Back in Wireshark, filter for RDP traffic only (tcp.port == 2289).
</p>
<img src="https://i.imgur.com/IC6Xemr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
