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

- 1 - Create File Share Folders
- 2 - Set Permissions
- 3 - Attempt to access file shares
- 4 - Create Security Groups

<h2>ACTIONS AND OBSERVATIONS</h2>

1 - Create File Share Folders
<p>
<img src="https://i.imgur.com/4kpWWbx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Created for new folders named Read-Access, Write-Access, and No-Access.
</p>
<br />

2 - Set Permissions and Share Files
<p>
<img src="https://i.imgur.com/iKbpEaf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/7ousuSe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


3 - Attempt to access file shares and folders
<p>
<img src="https://i.imgur.com/ulQTnb5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/b6rBbaL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Clicked on No-Access folder to check permissions. Windows will not allow access to the folder. Permissions are working correctly here.

After clicking Read-Access folder and trying not create a folder (write) this notification popped up. Permissions set to only read and not write or create folders/documents. The permissions are working correctly.
</p>
<br />
Write In Folders
<p>
<img src="https://i.imgur.com/n9h4qhH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>

Clicked on the Write-Access folder. Created a text file and named it test. The permissions are working correctly for this folder. This folder has read & write permissions.
</p>
<br />

Create new organizational unit and group in Client-1: _SECURITY GROUPS AND ACCOUNTANTS
<p>
<img src="https://i.Imgur.com/Gvtrf9l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/6sBHKB9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

4 - Create organizational unit: _SECURITY GROUPS
  
Create security group: ACCOUNTANTS
</p>
<br />

<p>
<img src="https://i.imgur.com/CSbmHZ0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating the new organizational unity and group, go back to DC-1 to set permissions in accounting folder.  Open File Explorer, click on "this PC" and then Windows C:, right-click on accounting, and select properties.  Then type ACCOUNTANTS and click add, change permissions to "Read/Write", and click share.  
</p>
<br />

Add user to ACCOUNTANTS group
<p>
<img src="https://i.imgur.com/1l2eiiV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Go back to Active Directory Users and Computers in Client-1.  Go to _SECURITY GROUPS and doubl-click ACCOUNTANTS, click Members tab, enter name of the user from DC-1 and click "check names".  Then click OK, click Apply, and OK again.  After adding user, head back to Client-1, open File Explorer, click Network, and open accounting.  A message should appear indicating that "Windows cannot access \\dc-1\accounting".  In order for the user to access the folder, the user must logoff from remote desktop and log in again; then the user can access the accounting folder.
