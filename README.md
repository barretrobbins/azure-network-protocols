<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>VIDEO DEMONSTRATION</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://youtu.be/kT8nFF5Zejw)

<h2>ENVIRONMENTS AND TECHNOLOGIES USED</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>OPERATING SYSTEMS USED </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>HIGH-LEVEL STEPS</h2>

- STEP 1 Create File Share Folders
- STEP 2 Set Permissions
- STEP 3 Attempt to access file shares
- STEP 4 Create Security Groups

<h2>ACTIONS AND OBSERVATIONS</h2>

Create File Share Folders
<p>
<img src="https://i.imgur.com/5XytNYh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Created for new folders named Read-Access, Write-Access, and No-Access.
</p>
<br />

Set Permissions
<p>
<img src="https://i.imgur.com/bEmKHX5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click the Sharing tab.
</p>
<br />

<p>
<img src="https://i.imgur.com/awzAQaM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Choose users to give access to the folder (Jane doe) and set their permission level (Read only).
</p>
<br />
<p>
<img src="https://i.imgur.com/7ousuSe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Attempt to access file shares
<p>
<img src="https://i.imgur.com/ulQTnb5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Clicked on No-Access folder to check permissions. Windows will not allow access to the folder. Permissions are working correctly here.
</p>
<br />

<p>
<img src="https://i.imgur.com/b6rBbaL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After clicking Read-Access folder and trying not create a folder (write) this notification popped up. Permissions set to only read and not write or create folders/documents. The permissions are working correctly.
</p>
<br />

<p>
<img src="https://i.imgur.com/n9h4qhH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Clicked on the Write-Access folder. Created a text file and named it test. The permissions are working correctly for this folder. This folder has read & write permissions.
</p>
<br />

Create a security group
<p>
<img src="https://i.imgur.com/YPJLsLd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a new organizational unit in the Active Directory Domain.
</p>
<br />

<p>
<img src="https://i.imgur.com/DDnVPpy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Name it _SECURITY_GROUPS.
</p>
<br />

<p>
<img src="https://i.Imgur.com/Gvtrf9l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a new group within _SECURITY_GROUPS.
</p>
<br />

<p>
<img src="https://i.Imgur.com/g5GYnHm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Name the group ACCOUNTANTS, set the group type to security.
</p>
<br />
