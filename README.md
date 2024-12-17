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
<img src=https://github.com/user-attachments/assets/042f775a-77e0-4940-ab0a-e3c37f6a8533>
<br />
<br />

2. Create a Virtual Network
  - Set up a Virtual Network (VNet) and Subnet for the lab environment.
<img src=https://github.com/user-attachments/assets/24827c11-18f3-4f25-a7d9-682bd401fdfe>
<br />
<br />

3. Create a Windows 10 Virtual Machine
  - Use the previously created Resource Group and Virtual Network.
  - Allow Azure to automatically configure the network and subnet for the VM.
<img src=https://github.com/user-attachments/assets/6931c894-4886-40d8-be28-2bf10bf0f37c>
<br />
<br />

4. Create a Linux (Ubuntu) Virtual Machine
  - Use the same Resource Group and Virtual Network as the Windows VM.
  - Configure username/password for authentication.
<img src=https://github.com/user-attachments/assets/852b622d-8717-465d-88b7-766b6bbc3ef0>
<br />
<br />

5. Set Up Remote Desktop
  - Install Microsoft Remote Desktop if on a Mac.
  - Use Remote Desktop to connect to the Windows VM.
<img src=https://github.com/user-attachments/assets/e0c0b6c5-27ba-4fe7-a762-961cdda2fb35>
<br />
<br />

6. Install Wireshark on Windows VM
  - Open Wireshark and start capturing traffic.
  - Apply filters for specific traffic types:
    - ICMP: Observe ping requests between the two VMs.
        <img src=https://github.com/user-attachments/assets/71f0b748-e64e-4eee-bb44-86bdc3ac574e>
    - Public Traffic: Ping a website (e.g., www.google.com) from the Windows VM.
        <img src=https://github.com/user-attachments/assets/c7c2bc6a-372b-4f74-96e9-63d56f41ff55>
<br />
<br />

7. Modify Firewall Rules
  - Initiate a continuous ping (ping 10.0.0.5 -t) from Windows VM to Linux VM.
      <img src=https://github.com/user-attachments/assets/8b9f69e5-bc61-4261-baf0-d54b0f290d4b>
  - Block ICMP traffic in the Linux VM's Network Security Group and observe the effect in Wireshark.
      <img src=https://github.com/user-attachments/assets/cdea50ab-d125-4737-b161-d993b11a4a99>
  - Re-enable ICMP traffic and confirm it resumes in Wireshark.
      <img src=https://github.com/user-attachments/assets/c154612d-f5a6-4612-b2e2-ea9abdfbe8dc>
<br />
<br />

8. Analyze SSH Traffic
  - SSH into the Linux VM from the Windows VM using its private IP address.
  - Observe SSH traffic in Wireshark while executing commands.
      <img src=https://github.com/user-attachments/assets/58f11029-6683-4aca-9282-40c5a5f74a6b>
<br />
<br />

9. Analyze DHCP Traffic
  - Filter for DHCP traffic in Wireshark.
  - Create a simple .bat file combining the ipconfig /release and ipconfig /renew commands. We run them from the file because if we run them manually, we lose our remote connection to the window-vm.
  - Use PowerShell to run the .bat file which performs the ipconfig /release and ipconfig /renew commands.
      <img src=https://github.com/user-attachments/assets/c52e6035-67ac-4f3a-92b3-7fba7f6bc495>
  - Observe the DHCP traffic appearing in WireShark.
      <img src=https://github.com/user-attachments/assets/6dc6b70c-d28a-4340-ac96-944bec4f0a88>
<br />
<br />

10. Analyze DNS Traffic
  - Filter for DNS traffic in Wireshark.
  - Use nslookup to retrieve the IP addresses of websites (e.g., google.com, disney.com).
      <img src=https://github.com/user-attachments/assets/e9aae9a9-37d7-452d-9530-f0bcec05b941>
<br />
<br />

11. Observe RDP Traffic
  - Filter for RDP traffic (tcp.port == 3389) in Wireshark.
  - Note the continuous traffic due to the live RDP session.
      <img src=https://github.com/user-attachments/assets/e93bc74b-1e82-428c-8f26-83d8accb3294>
<br />
<br />

12. Close Connections
  - End the Remote Desktop session.
<br />
<br />

13. Delete Resources
  - Remove the Resource Groups and verify their deletion to avoid incurring charges.
<br />
