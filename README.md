<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create Virtual Machine in Azure
- Install PHP Manager for IIS
- Install osTicket v1.15.8
- Install HeidiSQL 

<h2>Installation Steps</h2>
<h3 align="center">Create Virutal Machine in Azure</h3>
<br />
<p>
	Create a Resource Group
</p>
<p>
	<img src="https://i.imgur.com/FSzc1eI.png" alt="Resource Group"/>
</p>
<p>
Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs (Central Processing Units).
When creating the VM, allow it to create a new Virtual Network (Vnet):
</p>
<br />
<img src="https://i.imgur.com/qoNH8gL.png" alt="Virtual Machine"/>

<img src="https://i.imgur.com/kdaXEpa.png" alt="Lab User Setup"/>
</p>
<br />
<br />
<h3 align="center">Connect to your Virtual Machine with Remote Desktop Connection</h3>
Use the VM's Public I.P. address to connect via Remote Desktop
<br />
<p>
<img src="https://i.imgur.com/2F41kny.png" alt="Remote Desktop Connection"/>
</p>
<br />
<br />
<h3 align="center">Install / Enable IIS in Windows</h3>
Go to control panel,click on programs, select turn windows features on or off, and add IIS
<br />
</p>
<p>
<img src="https://i.imgur.com/ILq51l4.png" alt="Install IIS"/>	
</p>
<br />
<p>
Next, we will open this installation file: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6 to install osTicket and some of the dependencies required.
<p>	
	<h3 align="center">Install PHP Manager for IIS and Rewrite Module</h3>
</p>
<p>
<img src="https://i.imgur.com/fmxi5wI.png" alt="Install PHP Manager and Rewrite Module"/>
</p>
<br />
<h3 align="center">Create the directory C:\PHP
<br />
</p>
<p>
<img src="https://i.imgur.com/aly5Aw0.png" alt="PHP C Drive" 
<br />    
<br />
<h3 align="center">From installation files, download next 3 items 
<br />	
<br />
<img src="https://i.imgur.com/hXA5bxc.png" alt="next 3 file downloads"/>
	
- For the file PHP 7.3.8 after downloading it, we will unzip all the contents into our PHP folder located on the C Drive.
	
- Download file VC_redistx86.exe (Microsoft Visual C++) as normal.
	
- Download MySQL 5.5 and launch Configuration Wizard after install. Choose Standard Configuration and set the password as Password1.
<br />
<br />
<h3 align="center"> Now open IIS as an administrator and register PHP
<br />
<br />	
<img src="https://i.imgur.com/hIirxSM.png" alt="PHP Manager"/>	

	
<h3 align="center">Download osTicket v1.15.8
	
- Download osTicket from the Installation Files Folder
- Extract and copy “upload” folder to c:\inetpub\wwwroot
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”


<img src="https://i.imgur.com/0UpFEXa.png" alt="Download osTicket"/>
<br />	
<br />    
 <h3 align="center"> Go to sites -> Default -> osTicket
<br />
<br />	 
<img src="https://i.imgur.com/FuUQbL8.png" alt="Default"/>
	 
<h3 align="center">Note that some extensions are not enabled
<br />
<br />
<img src="https://i.imgur.com/kvHqL4b.png" alt="Extensions"/>
<br />
<br />
	- Go back to IIS, sites -> Default -> osTicket
	
- Double-click PHP Manager
	
- Click “Enable or disable an extension”
	
- Enable: php_imap.dll
	
- Enable: php_intl.dll
	
- Enable: php_opcache.dll
	
- Refresh the osTicket site in your browse, observe the changes
	
<br />
<br />
	
<h3 align="center"> Rename and Assign Permissions to ost-config.php
<br />
<br />
<img src="https://i.imgur.com/SiCOLAQ.png" alt="ost-config"/>
<br />
<br />
- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php change ost-sampleconfig.php to ost-config.php
- Steps to assigning permissions are: Disable inheritance -> Remove All
New Permissions -> Everyone -> All
<br />
<br />
<h3 align="center"> Continue Setting up osTicket in the browser (click Continue)
<br />
<br />
<img src="https://i.imgur.com/dCbjweh.png" alt="osTicket Setup"/>
<br />
<br />
<h3 align="center">From Installation Files, download and install HeidiSQL
<br />
<br />
<img src="https://i.imgur.com/erk5kl8.png" alt="HeidiSQL"/>
<br />
<br />
At bottom of osTicket installation page:
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click Install Now
<br />
<br />
	
