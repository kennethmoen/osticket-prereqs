<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
The following project demonstates how to set up a fully functioning ticketing system through osTicket, one complete with an admin account, agent panel and a page where end users can submit tickets.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- PHP Manager
- Rewrite Module
- PHP 7.3.8
- VC_redist.x86
- MySQL
- OsTicket
- HeidiSQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/rwsDH3w.png"/>
</p>
<p>
Create a virtual machine in Azure that runs Windows 10 and has 2-4 cores. Once it's intiated connect to it with remote desktop and enable IIS. Do this by clicking on the search bar and searching control panel then go to programs and then click Windows features on or off and enable Internet Information Serves and then enable CGI inisde of Application Development Features and Common HTTP Features also make sure IIS Management Console is enabled inside of WebManagement Tools.
  
</p>
<br />

<p>
<img src="https://i.imgur.com/8h1Wvvb.png"/>
</p>
<p>
Open a web browser and type in 127.0.0.1 and if the installation worked then this page should appear. This address is the loopback address.
</p>
<br />

<p>
<img src="https://i.imgur.com/SYRLT8t.png"/>
</p>
<p>
Install PHP Manager band be sure to click download anyway. then install the rewrite module and do the same. Use these links: <br />
   <a href= "https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=share_link"> PHP Manager </a>
  <br />
  <a href= "https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link"> Rewrite Module </a>
</p>
<br />

<p>
<img src="https://i.imgur.com/7xgSxDS.png"/>
</p>
<p>
Create a folder in the C drive called PHP this is directory C:\PHP. Next install PHP 7.3.8 by using the link below: <br />
  <a href="https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link"> PHP 7.3.8</a>
</p>
<br />

<p>
<img src="https://i.imgur.com/zfLe0GP.png"/>
</p>
<p>
This will download a ZIP file go to downloads in file explore right click on the folder and extract to C:\PHP
</p>
<br />

<p>
<img src="https://i.imgur.com/urpGkfs.png"/>
</p>
<p>
Install VC_Redist and MySQL. The links will be below. When the setup wizard for MySQL launches do a typial and standard setup. Then set the password to be password1. <br \>
<a href="https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link"> VC </a> <br \>
<a href="https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=share_link"> MySQL </a> 
</p>
<br />

<p>
<img src="https://i.imgur.com/RtJ3X2v.png"/>
</p>
<p>
Go to the Windows search bar and type in Internet Information Services to open its management window. Click on PHP manager and then register PHP with the directory shown in the above screen shot. After registering PHP reload IIS.
</p>
<br />

<p>
<img src="https://i.imgur.com/cfzo00u.png"/>
</p>
<p>
Use the installation file link to install OsTicket and extract the upload folder to c:\inetpub\wwwroot  and rename it to osTicket then reload IIS. Be sure to be running IIS as an administrator <br \>
<a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation File </a>
</p>
<br />

<p>
<img src="https://i.imgur.com/T85wCxZ.png"/>
</p>
<p>
If every step was done correctly then you should see this screen when you click browse 80 on IIS after going to the Default Website branch on the left of the IIS managaer. 
</p>
<br />

<p>
<img src="https://i.imgur.com/o5jn685.png"/>
</p>
<p>
Go to the PHP manager and click on enable extensions and enable the extensions listed below by scrolling to it, right clicking and clicking enable rule: <br \>
Enable: php_imap.dll
  <br \>
Enable: php_intl.dll
  <br \>
Enable: php_opcache.dll

  
</p>
<br />

<p>
<img src="https://i.imgur.com/MhYRVn5.png"/>
</p>
<p>
Go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the file ost-config.php then right click it go to properties and then security. Go to permissions disable its inheritence then add a principal and give everyone read/write permission.
</p>
<br />

<p>
<img src="https://i.imgur.com/tttew8D.png"/>
</p>
<p>
Install Heidi SQL and use root/password1 as the login and create a database called osTicket. Do this by right clicking unnamed then going to create new and then database.<br \>
<a href="https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit"> HeidiSQL </a>
  
</p>
<br />

<p>
<img src="https://i.imgur.com/VZ2KRmQ.png"/>
</p>
<p>
Go to OsTicket in your web browser continue the setup by adding in these texts for these fields: <br \>
  MySQL Database: osTicket<br />
  MySQL Username: root <br \>
  MySQL Password: password1
  <br \>
This should complete the installationa and prompt you to begin the cleanup process which is to delete C:\inetpub\wwwroot\osTicket\setup and to set permissions to Read only for C:\inetpub\wwwroot\osTicket\include\ost-config.php This concludes the setup demonstration for osTicket.
</p>
<br />
