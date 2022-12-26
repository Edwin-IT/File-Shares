<p align="center">
<img src="https://imgur.com/kup8h6K.png" height="25%" width="25%" alt="DNS"/>
</p>

<h1>DNS</h1>
This tutorial helps build intuition for DNS by configuring A-Records and CNAME Record in DNS manager in a Domain Controller and seeing the effects in a Client Virtual Machine.<br />


<h2>Environments and Technologies Used</h2>

- Command line
- DNS Manager

<h2>Overview</h2>

- Step 1: Create some sample file shares with various permissions
- Step 2: Attempt to access file shares as a normal user
- Step 3: Create an “ACCOUNTANTS” Security Group, assign permissions, and test access



<h2>Steps</h2>

<p>
<img src=".png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=".png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Step 1: Log into DC-1 as domain admin account, and  log into Client-1 as a normal user with random account. In DC-1, in the C:\ drive, create 4 folders: “read-access”, “write-access”, “no-access”, and “accounting”. In “read-access” give Domain Users permission to “Read”.  In “write-access” give Domain Users permission to “Read/Write”. In “no-access” give Domain Admins permissions to “Read/Write”.
</p>
<br />

<p>
<img src=".png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Step 2: In Client-1, navigate to the shared folder. Some folders, the user can access, some, the user cannot.

</p>
<br />

<p>
<img src=".png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=".png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src=".png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Step 3: In DC-1, in Active Directory, create a security group called “ACCOUNTANTS”. Next, in the “accounting” folder, set “Read/Write” permissions for “ACCOUNTANTS”. In Client-1, try to access the accountants folder and It will fail. Go back to DC-1, and make the normal user a member of the “ACCOUNTANTS”  Security Group. Now try to access the “accounting” folder and it should work.
</p>
<br />
