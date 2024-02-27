<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Installation</h1>
This tutorial outlines the installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites and Installation Files</h2>

[CLICK ME](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

- IIS
- PHP Manager
- Rewrite Module
- PHP 7.3.8
- VC_redistx86
- MySQL
- HeidiSQL
- osTicket v1.15.8

<h2>Part 1: Create a Virtual Machine in Azure</h2>

1. Create a Resource Group:
    - Log in to the Azure Portal.
    - Search for "Resource groups" in the top search bar.
    - Click "Create" and provide a name for the new resource group, choose a region, and click "Review + create" and then "Create".

2. Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs:
    - Choose the appropriate Windows 10 image and follow the wizard to configure your VM.
       - Name: OsTicketSetupTutorial
       - Username: tutorial
       - Password: osTicketPassword1!
       - Choose a size between 2-4 vCPUs.
    - Allow the creation of a new Virtual Network (Vnet).

<h2>Part 2: Installation </h2>

1. Installation Files
    - Open the [INSTALLATION FILES](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) link provided.

2. Install/Enable IIS in Windows
    - Open the "Control Panel" on the Windows VM.
    - Navigate to "Programs" -> "Turn Windows features on or off."
    - Check the following:
        - World Wide Web Services -> Application Development Features -> [X] CGI, [X] Common HTTP Features
        - Internet Information Services -> Web Management Tools -> [X] IIS Management Console

3. Install PHP Manager for IIS
    - Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi).

4. Install Rewrite Module:
    - Download and install the Rewrite Module (rewrite_amd64_en-US.msi).

5. Create C:\PHP Directory

6. Download and Install PHP:
    - Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip it into C:\PHP.
    - If prompted, choose to "Keep" the file.

7. Download and Install VC_redist.x86.exe
     
8. Download and Install MySQL:
    - Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi).
    - Choose a Typical Setup and set the password to "Password1".
    - Launch the Configuration Wizard after installation and choose Standard Configuration.

9. Register PHP in IIS:

Open IIS as an administrator.
Register PHP from within IIS.
Reload IIS:

Stop and Start the IIS server.
Install osTicket v1.15.8:

Download osTicket from the Installation Files Folder.
Extract and copy the "upload" folder to C:\inetpub\wwwroot.
Rename "upload" to "osTicket".
Reload IIS.
Enable PHP Extensions:

Go to IIS -> sites -> Default -> osTicket.
Double-click PHP Manager.
Click "Enable or disable an extension".
Enable: php_imap.dll, php_intl.dll, php_opcache.dll.
Refresh the osTicket site in your browser.
Configure osTicket:

Rename ost-config.php from C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php.
Assign permissions to ost-config.php (Disable inheritance, Remove All, New Permissions -> Everyone -> All).
Continue Setting up osTicket:

In the browser, continue setting up osTicket by clicking "Continue".
Provide the necessary information, such as Helpdesk name and default email.
Install HeidiSQL:

Download and install HeidiSQL.
Open HeidiSQL, create a new session (root/Password1), and connect to the session.
Create MySQL Database:

Create a new database called "osTicket" using HeidiSQL.
Complete osTicket Setup:

Finish setting up osTicket in the browser.
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click "Install Now!"
Congratulations:

Browse to your help desk login page: http://localhost/osTicket/scp/login.php.
Clean Up:

Delete C:\inetpub\wwwroot\osTicket\setup.
Set permissions to "Read" only for C:\inetpub\wwwroot\osTicket\include\ost-config.php.
Notes:

Browse to your help desk login page: http://localhost/osTicket/scp/login.php.
End Users osTicket URL: http://localhost/osTicket/.


