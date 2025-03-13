<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial walks you through the installation of the OsTicket System through windows virtual machine as well as the required resources to peform this installation.

<h4>Sidenotes:</h4>

- The screenshots shown below are from macbook pro 13 (what I used)
- Your computer can use any operating system

<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual MachinesCompute)
- Windows 10 Pro (Done through Virtual Machine)
- Remote Desktop (RDP)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

<h3>Should have before doing this lab:</h3>

- Microsoft Azure Subscription

<h3>Will be done in this lab</h3>

- Create Virtual Machine in Mircrosoft Azure 
- Install OsTicket
- Install MySQL
- Install HeidiSQL
- Install PHP
- Install Microsoft Visual C++


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/mQTqNDo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into Microsoft Azure and head to the virtual machines tab. Click on the + Create Button and press create Azure Virtual Machine.
</p>



<p>
<img src="https://i.imgur.com/b77X0tQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

- **Create a new resource group:** `osTicket`  
- **Virtual machine name:** `osticket-vm`  
- **Select a region:** Any (just remember which one)  
- **Image:** `Windows 10 Pro, version 22Hz - x64 Gen2`  
- **Size:** Any (preferably 2/+ CPUs)  
- **Username and password:** Any (just remember them)  

</p>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Setup your remote desktop. If you are using MacOs as I was, you would need to first download "Windows App" from the app store. Open remote desktop then input public IP address found from the Virtual Machine just created in Microsoft Azure.
</p>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to the virtual machine through the remote desktop. You will open up the files downloaded in the beginning of this tutorial in the virtual machine just created. 
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You will need to enable IIS in Windows. Go to search bar type "Control Panel" > click "Turn Windows features on or off" > Check Internet Information Services box 
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You will then click into "World Wide Web Services" > Click "Application Development Features" > Check the "CGI" box. You have now enabled IIS in Windows with CGI
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You will then click into "World Wide Web Services" > Click "Application Development Features" > Check the "CGI" box. You have now enabled IIS in Windows with CGI
</p>

<h3> Installing PHP Manager </h3>




