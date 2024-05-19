<p align="center">
<img src="https://i.imgur.com/6fYfF9b.png"/>
</p>

<h1>Network File Shares & Permissions</h1>
This tutorial outlines the file shares and permissions on a network within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
  

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- File Shares with Various Permissions
- File Shares Access
- Creating An "Accountants" Security Group
- Security Group Exception
  

<h2> File Shares with Various Permissions </h2>

<p>
<img src="https://i.imgur.com/iImvp2F.png"/>
</p>
<p>
Select "Tools". <br /> <br />
Select "Active Directory Users and Computers". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/40sXCnl.png"/>
</p>
<p>
Select "_EMPLOYEES". <br /> <br />
Select desired employee. <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/sOYjwJ7.png"/>
</p>
<p>
Go to "Windows Pane". <br /> <br />
Select "File Explorer" - Folder Icon. <br /> <br />
Select "This PC". <br /> <br />
Select "Windows (C:)". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/1dKLOjW.png"/>
</p>
<p>
Create 4 folders and name them the following: <br /> <br />
(1) "read-access" <br /> <br />
(2) "write-access" <br /> <br />
(3) "no-access" <br /> <br />
(4) "accounting" <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/22KVsIS.png"/>
</p>
<p>
Select "read-access" folder. <br /> <br />
Right Click and Select "Properties". <br /> <br />
Select "Sharing". <br /> <br />
Select "Share". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/8B1Wn6G.png"/>
</p>
<p>
Type "Domain Users" and Select "Add".
</p>
<br />

<p>
<img src="https://i.imgur.com/456E0i2.png"/>
</p>
<p>
Select "Read" for the Permission Level. <br /> <br />
Select "Share". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/jbRlMJr.png"/>
</p>
<p>
Select "Done".
</p>
<br />

<p>
<img src="https://i.imgur.com/1St0fEM.png"/>
</p>
<p>
Select "Apply". <br /> <br />
Select "Close". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/YcWhxJQ.png"/>
</p>
<p>
Select "write-access" folder. <br /> <br />
Right Click and Select "Properties". <br /> <br />
Select "Sharing". <br /> <br />
Select "Share". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/8gcpBl4.png"/>
</p>
<p>
Type "Domain Users" and Select "Add". <br /> <br />
Select "Read/Write" for Permission Level. <br /> <br />
Select "Share". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/aBM5Q7H.png"/>
</p>
<p>
Select "Done".
</p>
<br />

<p>
<img src="https://i.imgur.com/HmmnZMI.png"/>
</p>
<p>
Select "Apply". <br /> <br />
Select "Close". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/NcQv3PU.png"/>
</p>
<p>
Select "no-access" folder. <br /> <br />
Right Click and Select "Properties". <br /> <br />
Select "Sharing". <br /> <br />
Select "Share". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/kFKJmoU.png"/>
</p>
<p>
Type "Domain Admins" and Select "Add". <br /> <br />
Select "Read/Write" for Permission Level. <br /> <br />
Select "Share". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/0ChyhAh.png"/>
</p>
<p>
Select "Done".
</p>
<br />

<p>
<img src="https://i.imgur.com/LNYZi8V.png"/>
</p>
<p>
Select "Apply". <br /> <br />
Select "Close". <br /> <br />
</p>
<br />

<h2> File Shares Access </h2>
<p>
<img src="https://i.imgur.com/c1BEI9r.png"/>
</p>
<p>
Go to "Remote Desktop Connection". <br /> <br />
Select "Connect". <br /> <br />
Select "More choices". <br /> <br />
Select "Use a different account". <br /> <br />
Enter Employee Username. <br /> <br />
Enter Employee Password. <br /> <br />
Select "Ok". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/vsc47mf.png"/>
</p>
<p>
Go to "File Explorer". <br /> <br />
Type "\\dc-1" in the search bar and Press "Enter". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/3900nGG.png"/>
</p>
<p>
Select "read-access" folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/2r4tdO8.png"/>
</p>
<p>
Select "write-access" folder. <br /> <br />
Right Click and Select "New Folder". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/mKssksW.png"/>
</p>
<p>
Select "no-access" folder. <br /> <br />
Only "Domain Admins" can access this folder hence access has been denied. <br /> <br />
</p>
<br />

<h2> Creating An "Accountants" Security Group </h2>
<p>
<img src="https://i.imgur.com/yCHIgrp.png"/>
</p>
<p>
Go to "Active Directory". <br /> <br />
Select "mydomain.com". <br /> <br />
Right Click and Select "New". <br /> <br />
Select "Organizational Unit". <br /> <br />
Name "_Security Groups". <br /> <br />
Select "Ok". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/yBfi6PW.png"/>
</p>
<p>
"_Security Groups" organizational unit has successfully been added to Active Directory.
</p>
<br />

<p>
<img src="https://i.imgur.com/6Va3TnX.png"/>
</p>
<p>
Select "mydomain.com". <br /> <br />
Right Click and Select "Refresh". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/mNb8I6r.png"/>
</p>
<p>
Select "_Security Groups". <br /> <br />
Right Click and Select "New". <br /> <br />
Select "Group". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/cRFfIJT.png"/>
</p>
<p>
Group Name: Accountants. <br /> <br />
Group Type: Security. <br /> <br />
Select "Ok". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/x7SlIGs.png"/>
</p>
<p>
Go to "File Explorer". <br /> <br />
Select "This PC". <br /> <br />
Select "Windows (C:)". <br /> <br />
Select "accounting folder". <br /> <br />
Right Click and Select "Properties". <br /> <br />
Select "Sharing". <br /> <br />
Select "Share". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/wSaKYkL.png"/>
</p>
<p>
Type "Accountants" and Select "Add". <br /> <br />
Select "Read/Write" as Permission Level. <br /> <br />
Select "Share". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/zJqjHcK.png"/>
</p>
<p>
Select "Done".
</p>
<br />

<p>
<img src="https://i.imgur.com/fgQnzsI.png"/>
</p>
<p>
Select "Apply". <br /> <br />
Select "Close". <br /> <br />
</p>
<br />


<h2> Security Group Exception </h2>
<p>
<img src="https://i.imgur.com/jcXMZXL.png"/>
</p>
<p>
Return to "Active Directory". <br /> <br />
Select "_Security Groups". <br /> <br />
Right Click and Select "Properties". <br /> <br />
Select "Members". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/BqBUkdK.png"/>
</p>
<p>
Select "Add".
</p>
<br />

<p>
<img src="https://i.imgur.com/mcdGYhQ.png"/>
</p>
<p>
Type "selected employee's name". <br /> <br />
Select "Ok". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/bXeLpyB.png"/>
</p>
<p>
Select "Apply".
</p>
<br />

<p>
<img src="https://i.imgur.com/IfUlI1t.png"/>
</p>
<p>
Select "Ok".
</p>
<br />

<p>
<img src="https://i.imgur.com/j1ICnj6.png"/>
</p>
<p>
Go to "File Explorer". <br /> <br />
Type "\\dc-1" in the search bar and Press "Enter". <br /> <br />
Select "accounting" folder. <br /> <br />
"No access" error message appears because newly granted access will take place during next login. <br /> <br />
Select "Close". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/N6w9f8b.png"/>
</p>
<p>
Go to "Command Prompt". <br /> <br />
Type "logoff" and Press "Enter". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/TWLKZPt.png"/>
</p>
<p>
Login to "Client-1" with the same employee credentials. <br /> <br />
Go to "Windows Pane". <br /> <br />
Type "Run" in search bar and Press "Enter". <br /> <br />
Type "\\dc-1" and Select "Ok". <br /> <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/Yiz5ukB.png"/>
</p>
<p>
Select "accounting" folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/Ozv1rqY.png"/>
</p>
<p>
Create a new folder called "Q2 Reports". <br /> <br />
Congratulations you have completed this tutorial. <br /> <br />
</p>
<br />
