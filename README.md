<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial walks you through the installation of the OsTicket System through windows virtual machine as well as the required resources to peform this installation.

<h4>Sidenotes:</h4>

- The screenshots shown below are from macbook pro 13 (what I used)
- Your computer can use any operating system

<h2>Download This File First:</h2>

<p>
    <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD" target="_blank">
     osTicket-Installation-Files
    </a>
</p>

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
<img src="https://i.imgur.com/s2mUK5U.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Login to the virtual machine through the remote desktop. You will open up the files downloaded in the beginning of this tutorial in the virtual machine just created. 
</p>

<br/>
<p>
<img src="https://i.imgur.com/b6zoCFX.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
You will need to enable IIS in Windows. Go to search bar type "Control Panel" > Under Programs click "uninstall a program" > click "Turn Windows features on or off" > Check Internet Information Services box 
</p>
<br/>
<p>
<img src="https://i.imgur.com/swzA81u.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
You will then click into "World Wide Web Services" > Click "Application Development Features" > Check the "CGI" box. You have now enabled IIS in Windows with CGI
</p>
<br/>
<p>
<img src="https://i.imgur.com/Re5xrV9.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>


<h3 align="center"> Installing PHP Manager </h3>


<p align="center">
Inside osTicket-Installation-Files click and open "PHPManagerForIIS_V1 5.0 msi". Agree and click next, accepting all steps in order to install
</p>
<br/>
<p>
<img src="https://i.imgur.com/Ap2qO5O.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Installing Rewrite Manager </h3>

<p align="center">
Inside osTicket-Installation-Files click and open "rewrite_amd64_en-US.msi". Agree and click next, accepting all steps in order to install
</p>
<br/>
<p>
<img src="https://i.imgur.com/E1Jzroz.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Create directory called C:\PHP </h3>

<p align="center">
Open search bar and click on file explorer. Go to the Windows(C:) and create a new folder called "PHP". Inside osTicket-Installation-Files right click on "php-7.3.8-nts-Win32-VC15-x86.zip" and extract all, make sure to browse to the PHP folder we just created in the Windows(C:) drive. Select that folder and click extract.
</p>
<br/>
<p>
<img src="https://i.imgur.com/f5w5l7U.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Download VC_redist </h3>

<p align="center">
Click on "VC_redist.x86.exe" in the google doc and click next and agree to all terms.
</p>
<br/>
<p>
<img src="https://i.imgur.com/MhHrs0R.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Download MySQL </h3>

<p align="center">
Click on "MySQL 5.5.62" link right here: https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view and click next and agree to all terms. When on the Choose Setup Type screen, click on "Typical" then finish downloading. When prompted choose "Standard Configuration". For new root password and confirm just make a easy password. Can be something as easy as "root". A good practice is to have it saved on notepad in the virtual machine.
</p>
<br/>
<p>
<img src="https://i.imgur.com/iua85Hn.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Configurations in IIS </h3>

<p align="center">
Open Internet Information Services (IIS) Manager in Windows search bar. Open PHP Manager > Register new PHP version > Browse to PHP folder made in Windows(:C) drive > open "php-cgi" application
</p>
<br/>
<p>
<img src="https://i.imgur.com/LD992m9.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
In Internet Information Services (IIS) Manager, stop and start IIS by two ways: (1) under actions > stop > start (2) under connections > right click "osticket-vm" > stop > start
</p>
<br/>
<p>
<img src="https://i.imgur.com/PyJQdjV.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Install OsTicket </h3>

<p align="center">
In “osTicket-Installation-Files” right-click and extract "osTicket-v1.15.8.zip" into the same location ("osTicket-Installation-Files”). Copy the upload folder inside the "osTicket-v1.15.8.zip" folder we just extracted, and paste it into the Windows(C:) > inetpub > wwwroot folder.
</p>

<p align="center">
    <strong>CRITICAL STEP: Rename it "osTicket".</strong> 
</p>
<br/>
<p>
<img src="https://i.imgur.com/dRZM9ty.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Reload IIS </h3>

<p align="center">
Open IIS as Admin (right click on IIS and click "run as administrator" In Internet Information Services (IIS) Manager, stop and start IIS by two ways: (1) under actions > stop > start (2) under connections > right click "osticket-vm" > stop > start. Go to sites -> Default -> osTicket. On the right, click “Browse *:80”
</p>
<br/>
<p>
<img src="https://i.imgur.com/MVolxI1.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> OsTicket configurations </h3>

<p align="center">
Go back to IIS. Click on sites -> Default -> osTicket > Double-click PHP Manager
> Click “Enable or disable an extension”
Enable 3 things: (1) php_imap.dll (2) php_intl.dll (3) php_opcache.dll. Refresh the osTicket site in your browser, observe the changes
</p>
<br/>
<p>
<img src="https://i.imgur.com/xH9kfMd.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Rename "ost-config.php" files in Windows(C:) drive. C: > inetpub > wwwroot > osTicket > include > rename "ost-sampleconfig.php" to "ost-config.php" 
</p>
<br/>
<p>
<img src="https://i.imgur.com/SI1NVc4.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Right click "ost-config.php" > Properties > Security > Advanced > Disable Inheritance > Remove all inherited permissions from this object. Add > Select a Principal > Under "Enter the object name to select (examples) write: "everyone" > click "Check Names" > OK > Click "Full Control" > OK > highlight the only entry "Allow | Everyone" > OK. 
</p>
<br/>
<p>
<img src="https://i.imgur.com/Or1qbre.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Final OsTicket configurations </h3>

<p align="center">
On the osTicket Installer from the browser, click "continue".  
</p align="center">
<br/>
<ul>
  <li><strong>Helpdesk Name:</strong> whatever you want</li>
  <li><strong>Default email:</strong> make it up but save to use later</li>
  <li><strong>Email:</strong> Make it up but different from the first and save (this is your admin user)</li>
  <li><strong>Username and password:</strong> Same one you made and remembered from the beginning of the tutorial</li>
</ul>
<p>
<br/>

<img src="https://i.imgur.com/iI5jn1r.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Install HeidiSQL </h3>

<p align="center">
Open “osTicket-Installation-Files” > HeidiSQL_12.3.0.6589_Setup > Agree and accept all terms to install. Click + New > user and password: root / root > Open
</p>
<br/>
<p>
<img src="https://i.imgur.com/mlBnyu7.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Create database called "osTicket". Right click "Unamed" on left column > create new > database > name: "osTicket" > OK. 
</p>
<br/>
<p>
<img src="https://i.imgur.com/KIofPA6.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center"> Continue Setting Up osTicket in Browser </h3>
<br/>
<p align="center">
MySQL Database: "osTicket" | MySQL Username: root -- MySQL Password: root > install now
</p>
<br/>
<p>
<img src="https://i.imgur.com/bEqMnIm.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Check if osTicket installed. Go back to HeidiSQL > right click osTicket in left column and click refresh. Should have a lot of new entries.
</p>
<br/>
<p>
<img src="https://i.imgur.com/bEqMnIm.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<p align="center">
Browse to these two sites to make sure they load:
<br/>
end users ticket URL: http://localhost/osTicket/ 
<br/>
help desk login page: http://localhost/osTicket/scp/login.php
</p>
<br/>
<p>
<img src="https://i.imgur.com/s6IvrdD.png" height="75%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<br/>

<h3 align="center">Congratulations you are finished with the osTicket system setup!</h3>



