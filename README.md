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

<br/>
<p align="center">
Log into Microsoft Azure and head to the virtual machines tab. Click on the + Create Button and press create Azure Virtual Machine.
</p>
<p>
<img align="center" src="https://i.imgur.com/mQTqNDo.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>

- **Create a new resource group:** `osTicket`  
- **Virtual machine name:** `osticket-vm`  
- **Select a region:** Any (just remember which one)  
- **Image:** `Windows 10 Pro, version 22Hz - x64 Gen2`  
- **Size:** Any (preferably 2/+ CPUs)  
- **Username and password:** Any (just remember them)  

</p>
<br/>
<p>
<img src="https://i.imgur.com/b77X0tQ.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Setup your remote desktop. If you are using MacOs as I was, you would need to first download "Windows App" from the app store. Open remote desktop then input public IP address found from the Virtual Machine just created in Microsoft Azure.
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Login to the virtual machine through the remote desktop. You will open up the files downloaded in the beginning of this tutorial in the virtual machine just created. 
</p>

<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>
You will need to enable IIS in Windows. Go to search bar type "Control Panel" > click "Turn Windows features on or off" > Check Internet Information Services box 
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>
You will then click into "World Wide Web Services" > Click "Application Development Features" > Check the "CGI" box. You have now enabled IIS in Windows with CGI
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>
You will then click into "World Wide Web Services" > Click "Application Development Features" > Check the "CGI" box. You have now enabled IIS in Windows with CGI
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>


<h3> Installing PHP Manager </h3>
<br/>

<p>
Inside osTicket-Installation-Files click and open "PHPManagerForIIS_V1 5.0 msi". Agree and click next, accepting all steps in order to install
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Installing Rewrite Manager </h3>
<br/>
<p>
Inside osTicket-Installation-Files click and open "rewrite_amd64_en-US.msi". Agree and click next, accepting all steps in order to install
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Create directory called C:\PHP </h3>
<br/>
<p>
Open search bar and click on file explorer. Go to the Windows(C:) and create a new folder called "PHP". Inside osTicket-Installation-Files right click on "php-7.3.8-nts-Win32-VC15-x86.zip" and extract all, make sure to browse to the PHP folder we just created in the Windows(C:) drive. Select that folder and click extract.
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Download VC_redist </h3>
<br/>
<p>
Click on "VC_redist.x86.exe" in the google doc and click next and agree to all terms.
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Download MySQL </h3>
<br/>
<p>
Click on "MySQL 5.5.62" link in the google doc and click next and agree to all terms. When on the Choose Setup Type screen, click on "Typical" then finish downloading. When prompted choose "Standard Configuration". For new root password and confirm just make a easy password. Can be something as easy as "root". A good practice is to have it saved on notepad in the virtual machine.
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Configurations in IIS </h3>
<br/>
<p>
Open Internet Information Services (IIS) Manager in Windows search bar. Open PHP Manager > Register new PHP version > Browse to PHP folder made in Windows(:C) drive > open "php-cgi" application
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>
In Internet Information Services (IIS) Manager, stop and start IIS by two ways: (1) under actions > stop > start (2) under connections > right click "osticket-vm" > stop > start
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Install OsTicket </h3>
<br/>
<p>
In “osTicket-Installation-Files” right click and extract "php-7.3.8-nts-Win32-VC15-x86.zip". Copy upload folder inside of the "php-7.3.8-nts-Win32-VC15-x86" folder we just extracted, paste it into the Windows(C:) > inetpub > wwwroot folder.
  
<strong>CRITICAL STEP: Rename it "osTicket". </strong> 
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Reload IIS </h3>
<br/>
<p>
Open IIS as Admin (right click on IIS and click "run as administrator" In Internet Information Services (IIS) Manager, stop and start IIS by two ways: (1) under actions > stop > start (2) under connections > right click "osticket-vm" > stop > start. Go to sites -> Default -> osTicket. On the right, click “Browse *:80”
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> OsTicket configurations </h3>
<br/>
<p>
Go back to IIS. Click on sites -> Default -> osTicket > Double-click PHP Manager
> Click “Enable or disable an extension”
Enable 3 things: (1) php_imap.dll (2) php_intl.dll (3) php_opcache.dll. Refresh the osTicket site in your browser, observe the changes
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>
Rename "ost-config.php" files in Windows(C:) drive. C: > inetpub > wwwroot > osTicket > include > rename "ost-sampleconfig.php" to "ost-config.php" 
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>
Right click "ost-config.php" > Properties > Security > Advanced > Disable Inheritance > Remove all inherited permissions from this object. Add > Select a Principal > Under "Enter the object name to select (examples) write: "everyone" > click "Check Names" > OK > Click "Full Control" > OK > highlight the only entry "Allow | Everyone" > OK. 
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Final OsTicket configurations </h3>
<br/>
<p>
On the osTicket Installer from the browser, click "continue".  
</p>
<br/>
<ul>
  <li><strong>Helpdesk Name:</strong> whatever you want</li>
  <li><strong>Default email:</strong> make it up but save to use later</li>
  <li><strong>Email:</strong> Make it up but different from the first and save (this is your admin user)</li>
  <li><strong>Username and password:</strong> Same one you made and remembered from the beginning of the tutorial</li>
</ul>
<p>
<br/>

<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Install HeidiSQL </h3>
<br/>
<p>
Open “osTicket-Installation-Files” > HeidiSQL_12.3.0.6589_Setup > Agree and accept all terms to install. Click + New > user and password: root / root > Open
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>
Create database called "osTicket". Right click "Unamed" on left column > create database > name: "osTicket" > OK. 
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3> Continue Setting Up osTicket in Browser </h3>
<br/>
<p>
MySQL username: "osTicket" -- password: root -- username: root > install now
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>
Check if osTicket installed. Go back to HeidiSQL > right click osTicket in left column and click refresh. Should have a lot of new entries.
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p>
Browse to these two sites to make sure they load:
<br/>
end users ticket URL: http://localhost/osTicket/ 
<br/>
help desk login page: http://localhost/osTicket/scp/login.php
</p>
<br/>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3>Congratulations you are finished with the osTicket system setup!</h3>



