<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Installation</h1>
This tutorial will guide you through the installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites and Installation Files</h2>

[List of Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

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
3. Log into Virtual Machine.
   
<h2>Part 2: Installation </h2>

1. Installation Files
    - Open the [INSTALLATION FILES](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) link provided (**IN THE VIRTUAL MACHINE**)

2. Install/Enable IIS in Windows
    - Open the "Control Panel" on the Windows VM.
    - Navigate to "Programs" -> "Turn Windows features on or off."
    - Check the following:
        - World Wide Web Services -> Application Development Features -> [X] CGI, [X] Common HTTP Features
        - Internet Information Services -> Web Management Tools -> [X] IIS Management Console
![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/cee65396-6072-411b-a4ba-35c1ec484232)

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
    - Choose a Typical Setup.
    - Launch the Configuration Wizard after installation, choose Standard Configuration, and set the password to whatever you would like(for this tutorial I will use "Password1")

9. Register PHP in IIS:
    - Open IIS as an administrator.
    - Register PHP from within IIS.
        - Choose php-cgi as the file path when prompted
    - Reload IIS:
        - Stop and Start the IIS server.
![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/418a72b5-8e5a-4e48-9b81-7800530abd2c)
![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/95783c1e-e39c-4cfb-8855-c42785b10170)


10. Install osTicket v1.15.8:
    - Download osTicket from the Installation Files Folder.
    - Extract and copy the "upload" folder to C:\inetpub\wwwroot.
    - Rename "upload" to "osTicket".

11. Reload IIS and navigate to (http://localhost/osTicket/scp/login.php) in a browse on your virtual machine.

12. Enable PHP Extensions:
    - Go to IIS -> sites -> Default -> osTicket.
    - Double-click PHP Manager.
    - Click "Enable or disable an extension".
        - Enable: php_imap.dll, php_intl.dll, php_opcache.dll.
    - Refresh the osTicket site in your browser.

13. Configure osTicket:
    - Rename ost-config.php from C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php.
    - Assign permissions to ost-config.php (Disable inheritance, Remove All, Add -> Select a principle -> Everyone(check names) -> All).
    ![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/5732352a-4d31-4efd-9b93-ec9b0398b77a)
    ![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/f3e0b45a-25f8-4e4d-847e-2281c7d80336)
    ![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/25166b45-6336-4509-b79c-ac7cd410b74e)

      

14. Continue Setting up osTicket:
    - In the browser, continue setting up osTicket by clicking "Continue".
    - Provide the necessary information, such as Helpdesk name and default email.

15. Install HeidiSQL:
    - Download and install HeidiSQL.
    - Open HeidiSQL, create a new session (root/Password1), and connect to the session.
    - Create a new database called "osTicket" using HeidiSQL.
    ![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/2f9bb40e-b39c-4236-916c-76a9634877a9)
    ![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/ce11e517-2b64-41a9-889e-46e01e6ee6dc)
    ![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/296c9d86-fb94-4d3c-95c3-1ea93e0eef56)




16. Complete osTicket Setup:
    - Finish setting up osTicket in the browser.
        - MySQL Database: osTicket
        - MySQL Username: root
        - MySQL Password: Password1
    - Click "Install Now!"

**Clean Up:**
    
    - Delete C:\inetpub\wwwroot\osTicket\setup.
    - Set permissions to "Read" only for C:\inetpub\wwwroot\osTicket\include\ost-config.php.
![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/1afeb266-8717-4fa7-b917-1842d36ee115)
![image](https://github.com/mehmhacimic/osTicket-installation/assets/157438082/a91955dc-569c-440a-b950-983e8fcbc227)


**Congratulations! The setup is complete!**

Browse to your help desk login page: http://localhost/osTicket/scp/login.php.

End Users osTicket URL: http://localhost/osTicket/.


