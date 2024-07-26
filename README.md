<p align="center">
<img src="https://i.imgur.com/rJzxgW2.png" alt="A File Sharing Logo"/>
</p>

<h1>Network File Sharing and Permissions</h1>
This tutorial outlines how to implement the use of file sharing with various permissions between Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Implement the use of file sharing between Azure Virtual Machines](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services


<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Steps for File Sharing w/ Permissions</h2>

- Create sample file shares with specific permissions
- Attempt to access file shares as a normal domain user
- Create an “ACCOUNTANTS” Security Group, assign permissions, and test access to each file

<h2>File Sharing Steps</h2>

<p>
<img src="https://i.imgur.com/ys3rYH9.png" height="80%" width="80%" alt="Creating F0lders/Setting Permissions"/>
<img src="https://i.imgur.com/O2fWxxO.png" height="80%" width="80%" alt="Creating F0lders/Setting Permissions 1"/>
<img src="https://i.imgur.com/GmFz2H5.png" height="80%" width="80%" alt="Creating F0lders/Setting Permissions 2"/>
<img src="https://i.imgur.com/ojoCztZ.png" height="80%" width="80%" alt="Creating F0lders/Setting Permissions 3"/>
</p>
<p>
In the first step, inside of DC-1, we created four folders named READ-ACCESS, WRITE-ACCESS, NO-ACCESS, AND ACCOUNTING.  We shared READ-ACCESS with "Domain Users" group, and the permission level is set at "Read".  We shared WRITE-ACCESS with "Domain Users" group, and the permission level is set at "Read/Write".  We shared NO-ACCESS with "Domain Admins" group, with the permission level set at "Read/Write". (Nothing is done to ACCOUNTING folder for now).
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Accessing Folders as Domain User from Client-1"/>
</p>
<p>
In the 2nd step, inside of Client-1 as one of the random domain users, we found the file directory to the shared files from DC-1.  When we try to access the WRITE-ACCESS folder as the user on Client-1, we can read and also edit/change the file as we wish.  When try to access the READ-ACCESS folder with the same user, we can only read the contents of the file, but we cannot edit or change anything inside of the file.  When we try to access the NO-ACCESS folder, we cannot look into or access the contents of the folder at all.  This because the "Domain Users" group was not added on as users that are allowed access to it.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
