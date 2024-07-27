<p align="center">
<img src="https://i.imgur.com/rJzxgW2.png" alt="A File Sharing Logo"/>
</p>

<h1>Network File Sharing and Permissions</h1>
This tutorial outlines how to implement the use of file sharing with various permissions between Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Implement the use of file sharing between Azure Virtual Machines](https://www.youtube.com/watch?v=RgsrQQPN09U)

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
<img src="https://i.imgur.com/Jes2otu.png" height="80%" width="80%" alt="Accessing Folders as Domain User from Client-1"/>
<img src="https://i.imgur.com/tzezgHi.png" height="80%" width="80%" alt="Accessing Folders as Domain User from Client-1a"/>
<img src="https://i.imgur.com/SG9B7Qd.png" height="80%" width="80%" alt="Accessing Folders as Domain User from Client-1b"/>
<img src="https://i.imgur.com/9SUhfHl.png" height="80%" width="80%" alt="Accessing Folders as Domain User from Client-1c"/>
</p>
<p>
In the 2nd step, inside of Client-1 as one of the random domain users, we found the file directory to the shared files from DC-1.  When we try to access the WRITE-ACCESS folder as the user on Client-1, we can read and also edit/change the file as we wish.  When try to access the READ-ACCESS folder with the same user, we can only read the contents of the file, but we cannot edit or change anything inside of the file.  When we try to access the NO-ACCESS folder, we cannot look into or access the contents of the folder at all.  This because the "Domain Users" group was not added on as users that are allowed access to it.
</p>
<br />

<p>
<img src="https://i.imgur.com/LTNYCds.png" height="80%" width="80%" alt="Assigning Permissions to Accountants F0lder"/>
<img src="https://i.imgur.com/v8ChL5j.png" height="80%" width="80%" alt="Assigning Permissions to Accountants F1lders"/>
<img src="https://i.imgur.com/P0DjoAU.png" height="80%" width="80%" alt="Assigning Permissions to Accountants F2lder"/>
<img src="https://i.imgur.com/555Vltq.png" height="80%" width="80%" alt="Assigning Permissions to Accountants F3lders"/>
<img src="https://i.imgur.com/84t9p4S.png" height="80%" width="80%" alt="Assigning Permissions to Accountants F4lder"/>
<img src="https://i.imgur.com/784kD1H.png" height="80%" width="80%" alt="Assigning Permissions to Accountants F5lders"/>
<img src="https://i.imgur.com/jTyejz0.png" height="80%" width="80%" alt="Assigning Permissions to Accountants F6lder"/>
</p>
<p>
In the last step, inside of  DC-1, in Active Directory,  we created a security group called “Accountants”.  Then, in the “accounting” folder that we created earlier, we shared the contents on the folder with the same security group named “Accountants”,  with the permissions of “READ/WRITE”.  This action gives any user inside of the "Accountants" group the ability to read and edit/change files with the "Accounting" folder.  Inside of Client-1, as one of the random users, we tried to access the accountants folder, but it failed, and we logged out of Client-1 as that user.  On DC-1, we made that same particular user a member of the “Accountants” Security Group.  We then signed back into Client-1 as the user,  tried to access the “accounting” shared folder in DC-1, and now we have access to the folder.  We can read, write, and edit files inside of the "accounting" folder as we wish.



</p>
<br />
