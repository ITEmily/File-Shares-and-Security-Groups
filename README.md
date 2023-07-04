# 
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Using Active Directory to Create File Shares and Security Groups</h1>
This tutorial outlines the Use of Active Directory within Azure Virtual Machines to create File Shares and Security Groups with various permissions.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Active Directory Domain Services
  

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Create sample file shares with various permissions.
- Step 2: Access the file shares as a normal user. 
- Step 3: Create an "ACCOUNTANTS" Security Group and assign permissions.
 <br />
<br />
 

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/iK7HpGD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 1: Create sample file shares with various permissions. Using the Domain Controller and Virtual Machine created in the "Configuring On-premises Active Directory within Azure VMs" project, log into DC-1.  On the C:\ drive and create 4 folders: "read-access", "write-access", "no-access", and "accounting".  Set the following permissions (share the folder) for the "Domain Users" group: Set the folder "read-access" Domain Users permissions to "Read".  Set the folder "write-access" Domain Users permissions to "Read/Write".  And Finally, set the folder "no-access" Domain Admins permissions to "Read/Write".  (Skip the accounting folder for now.)
</p>
<br />
<br />
<br />

<p>
<img src="https://i.imgur.com/KNXTle0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 2: Access the file shares as a normal user. On Client-1 navigate to the shared folder (start, run, \\dc-1) Try to access the folders you just created and see what you are able to read, write and access.
</p>
<br />
<br />
<br />

<p>
<img src="https://i.imgur.com/5ecA4od.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3: Create an "ACCOUNTANTS" Security Group and assign permissions. Go back to DC-1 and create a security group called "ACCOUNTANTS".  On the accounting folder that was created earlier, set the permissions for the ACCOUNTANTS for "Read/Write".  Log out of Client-1 Log back in and check that you can access the accounting share in \\DC-1.  (Note, I had to restart the VM on Microsoft Azure before the change of permission took place.)
</p>
<br />

