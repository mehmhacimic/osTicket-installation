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

<h2>List of Installation Files</h2>

https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

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

