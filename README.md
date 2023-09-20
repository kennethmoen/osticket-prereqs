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
![image](https://github.com/kennethmoen/osticket-prereqs/assets/145589069/1bb9af82-93ac-48e1-ba48-2de50cf52cd4)

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- In Azure create a virtual machine using windows 10
- install/enable IIS in windows W/ CGI & Common HTTP Features
- Install Files needed to run osTicket System
- Register PHP from within IIS
- Install osTicket system

<h2>Installation Steps</h2>

<p>
<img src="https://github.com/kennethmoen/osticket-prereqs/assets/145589069/4585de2a-db93-4798-87be-24f0ce1a8789" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into Azure and create your resource group and virtual machine using windows 10 (2-4 virtual CPUS) and allowing the Virtual network to create a new Vnet. Name the Virtual Machine: Vm-osTicket create a username and password. I recommend writing it down or typing it in notepad and saving the information. Log in to your virtual machine via remote desktop.
</p>
<br />

<p>
<img src="https://i.imgur.com/3tekzq9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Once logged into the virtual machine open the IIS system from the control pannel. once the control pannel is open go to programs and turn windows features on and off.
- Install / Enable IIS in Windows WITH
- CGI and Common HTTP Features
- World Wide Web Services -> Application Development Features ->
- [X] CGI
- [X] Common HTTP Features
- IIS Management Console
- Internet Information Services -> Web Management Tools -> IIS Management Console
- [X] IIS Management Console

<br />

<p>
<img src="https://i.imgur.com/L1KIV7C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

 After enabling the IIS features it's time to install the files for the osTicket System. Download and install:
- PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
- Create the directory C:\PHP
-From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
- From the Installation Files, download and install VC_redist.x86.exe.
- From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
                 -Typical Setup ->
                 -Launch Configuration Wizard (after install) ->
                 -Standard Configuration ->
                 -Password1

<br />
<p>
<img src="https://i.imgur.com/E5WKcPk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Register the PHP manger by right clicking on the IIS from the start menu and click run as Administrator. 
- Go to PHP Manager and then click Register new PHP version
- C:// php.cgi folder
- restart the IIS Server

<br />

<p>
<img src="https://i.imgur.com/eqFSUiY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

Install osTicket v1.15.8
- Download osTicket from the Installation Files Folder
- Extract and copy “upload” folder to c:\inetpub\wwwroot
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
Reload IIS (Open IIS, Stop and Start the server)
Go to sites -> Default -> osTicket
- On the right, click “Browse *:80”
Note that some extensions are not enabled
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
- Refresh the osTicket site in your browse, observe the changes
Rename: ost-config.php
- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
Assign Permissions: ost-config.php
- Disable inheritance -> Remove All
- New Permissions -> Everyone -> All
Continue Setting up osTicket in the browser (click Continue)
- Name Helpdesk
- Default email (receives email from customers)
From the Installation Files, download and install HeidiSQL.
- Open Heidi SQL
- Create a new session, root/Password1
- Connect to the session
- Create a database called “osTicket”
Continue Setting up osticket in the browser
- MySQL Database: osTicket
- MySQL Username: root
- MySQL Password: Password1
- Click “Install Now!”

<br />
