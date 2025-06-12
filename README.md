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

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>

<p>
  
![Screenshot 2025-06-12 134605](https://github.com/user-attachments/assets/389b2846-b004-4842-a961-fdd61ba0fc78)

</p>
<p>
  
- Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI
- From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

</p>
<br />

<p>

  ![image](https://github.com/user-attachments/assets/92f7fc34-c27e-47ad-a95f-b3f54a95d489)

</p>
<p>
  
- Create the directory (in C drive) C:\PHP
- Unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
- Install VC_redist.x86.exe
- Install MySQL 5.5.62
    - Typical Setup ->
    - Launch Configuration Wizard (after install) ->
    -  Standard Configuration ->
    - Username: root (default, not for live use)
    - Password: root (default, not for live use)

</p>
<br />

<p>

  ![image](https://github.com/user-attachments/assets/46b5f620-a1a2-464f-aad6-d0c3782817aa)

</p>
<p>

- Open IIS as an Admin
- From IIS Register PHP (PHP Manager -> C:\PHP\php-cgi.exe)
- Restart IIS (from IIS, right click server, Stop and Start the server)
- From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
- Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
- Restart IIS (from IIS, right click server, Stop and Start the server)
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/d20634ef-0357-464c-a686-9613b693d750)

</p>
<p>

- From IIS expand "sites" -> expand "Default website" -> select "osTicket" -> On the right, "manage folder", click “Browse *:80”
- Note that some extensions are not enabled
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
- Refresh the osTicket site in your browser, observe the changes

</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/49df8eb2-1236-4084-9e37-46889f79721a)

</p>
<p>
  
- ASSIGN PERMISSIONS
- Right click ost-config.php-> properties->  security-> advanced
- Click on "Removed all inherited permissions"
- Click on "add"
- Click "select a principal"
- enter "everyone" (not for live environment)
- select ok-> apply-> ok

</p>
<br />

![image](https://github.com/user-attachments/assets/9b5fac84-2f36-4bf1-aa88-13bba1a4f291)

</p>
<p>
  
- Frome the browser, click "Continue" for osTicket, and Continue Setting up osTicket
- Name the Helpdesk
- Default email (receives email from customers)
- Make sure you keep track of usernames and passwords


</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/4ed2a7be-e70a-4297-aa67-553e8c4882d0)

</p>
<p>

- From the “osTicket-Installation-Files” folder, install HeidiSQL.
- Launch Heidi SQL
- Select "new" for new session
- Set up User and Password
- Select "open" To connect to the session to the database
- Create a database called “osTicket”
  - Right click on "unnamed"-> create new-> Database
  - Name the database "osTicket"-> click "ok"

  
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/44e5dac3-cc9a-4982-86df-593432c36315)

</p>
<p>

- In the browser finish configuring osTickete Installer
- MySQL Database: osTicket
- MySQL Username: root
- MySQL Password: root
- Click “Install Now”

With osTicket installed we need to do some cleanup
- We will want to delete the setup folder in our system
  - Delete: C:\inetpub\wwwroot\osTicket\setup.
    - Only delete the "setup" folder
- Finally set the permissions back to "Read" only in the ost-config.php file.

![image](https://github.com/user-attachments/assets/da4aa1c1-89e4-4393-a048-b1cb40656a2d)

  
</p>
