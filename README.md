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
