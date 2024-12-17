<img src="https://github.com/user-attachments/assets/6d1fd399-8e24-4ca3-b6ed-4ed6c7c07c9f" height="75%" width="75%">

<h1>Microsoft Azure: Virtual Machines & Networking</h1>
This lab focuses on using Microsoft Azure to create and configure virtual machines (VMs) and observe network traffic between them. The activity demonstrates Azure's capabilities in setting up a virtualized environment, using tools like Wireshark for traffic analysis, and applying basic networking principles such as ICMP, SSH, DHCP, and DNS. Participants also learn about configuring firewalls and managing network security groups.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Wireshark
<br />

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Linux (ubuntu 22.04)
<br />

<h2>Step-by-Step</h2>

1. Create a Resource Group
  - Open the Azure portal and create a new Resource Group.
<br />

2. Create a Virtual Network
  - Set up a Virtual Network (VNet) and Subnet for the lab environment.
<br />

3. Create a Windows 10 Virtual Machine
  - Use the previously created Resource Group and Virtual Network.
  - Allow Azure to automatically configure the network and subnet for the VM.
<br />

4. Create a Linux (Ubuntu) Virtual Machine
  - Use the same Resource Group and Virtual Network as the Windows VM.
  - Configure username/password for authentication.
<br />

5. Set Up Remote Desktop
  - Install Microsoft Remote Desktop if on a Mac.
  - Use Remote Desktop to connect to the Windows VM.
<br />

6. Install Wireshark on Windows VM
  - Open Wireshark and start capturing traffic.
  - Apply filters for specific traffic types:
    - ICMP: Observe ping requests between the two VMs.
    - Public Traffic: Ping a website (e.g., www.google.com) from the Windows VM.
<br />

7. Modify Firewall Rules
  - Initiate a continuous ping (ping 10.0.0.5 -t) from Windows VM to Linux VM.
  - Block ICMP traffic in the Linux VM's Network Security Group and observe the effect in Wireshark.
  - Re-enable ICMP traffic and confirm it resumes in Wireshark.
<br />

8. Analyze SSH Traffic
  - SSH into the Linux VM from the Windows VM using its private IP address.
  - Observe SSH traffic in Wireshark while executing commands.
<br />

9. Analyze DHCP Traffic
  - Filter for DHCP traffic in Wireshark.
  - Use PowerShell to renew the IP address of the Windows VM (ipconfig /renew).
<br />

10. Analyze DNS Traffic
  - Filter for DNS traffic in Wireshark.
  - Use nslookup to retrieve the IP addresses of websites (e.g., google.com, disney.com).
<br />

11. Observe RDP Traffic
  - Filter for RDP traffic (tcp.port == 3389) in Wireshark.
  - Note the continuous traffic due to the live RDP session.
<br />

12. Close Connections
  - End the Remote Desktop session.
<br />

13. Delete Resources
  - Remove the Resource Groups and verify their deletion to avoid incurring charges.
<br />
