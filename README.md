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

<h2>Installation Files</h2>

[CLICK ME](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<h2>Part 1: Create Virtual Machine in Azure</h2>

Create a Resource Group:
- Log in to the Azure Portal.
- Click on "Create a resource" and search for "Resource group".
- Click on "Create" and provide a name for the new resource group, choose a region, and click "Review + create" and then "Create".

Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs:
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
- Open "Control Panel" on the Windows VM.
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


