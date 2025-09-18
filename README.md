<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial aims to outline the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- IIS (Internet Information Services)
- PHP Manager
- VC_redistx86
- MySQL 5.5.62
- Rewrite Module
- Heidi SQL
<h2>Installation Steps</h2>

<p>
<img width="1386" height="1210" alt="Screenshot 2025-09-17 213415" src="https://github.com/user-attachments/assets/f50ebdc4-876d-4c55-a54b-bd63af2746fc" />
<img width="809" height="1074" alt="Screenshot 2025-09-17 213607" src="https://github.com/user-attachments/assets/379abdd2-069c-4cb6-a7be-9e2e037b9b7e" />

</p>
<p>
Before installing OS Ticket, we have to create a virtual machine (VM). Go on the VM page and click create--> make sure it is on the correct subscription--> resource group, create a new one and name it--> VM name, create a name--> region, select a region but for this tutorial, East US 2--> size, Standard_D2s_v3 - 2 vcpus, 8 GiB memory, administrator account, create a username and password and make sure to remember it--> check the Licensing box and leave evwerything else the way it is and click review and create then create.
</p>
<br />

<p>
<img width="1968" height="768" alt="Screenshot 2025-08-30 220141" src="https://github.com/user-attachments/assets/f4624e4c-22f5-4acd-ba12-4063605f3598" />
<img width="802" height="604" alt="Screenshot 2025-08-30 220415" src="https://github.com/user-attachments/assets/e17fe064-a006-4b04-8c05-b12631649de0" />
<img width="1200" height="678" alt="Annotation 2025-08-31 020711" src="https://github.com/user-attachments/assets/1a3a454b-043c-48fd-8264-28d857b258a0" />


</p>
<p>
Next, login into the VM but first obtain the public IP address by scrolling right on the VM page or by clicking on the VM itself-->open up remote desktop conneciton and enter the username and password that was created (may look different for MAC). You should be able to log into the VM.
</p>
<br />

<p>
<img width="1148" height="1162" alt="Annotation 2025-08-31 022049" src="https://github.com/user-attachments/assets/8131592a-61f9-42d9-98ad-84c49d2e81c4" />

</p>
<p>
Within the VM (osticket-vm), open the microsoft edge browser--> click and download the osTicket-Installation-Files.zip and unzip it onto your desktop. Once finished downloading, go to file explorer--> go to downloads--> drag the osTicket-installation-files folder onto the desktop--> right click it and click extract all--> click extract--> another folder should appear there and it should be the osTicket-Installation-Files folder.
</p>
<br />

<p>
<img width="1504" height="1184" alt="Annotation 2025-08-31 022520" src="https://github.com/user-attachments/assets/5d3fc2ba-d80f-4842-93a3-318f8bc924f4" />
<img width="906" height="1146" alt="Annotation 2025-08-31 022846" src="https://github.com/user-attachments/assets/b4016dbb-61fd-4f64-8fe2-e251755c8bb9" />
<img width="1874" height="1256" alt="Annotation 2025-08-31 023116" src="https://github.com/user-attachments/assets/175cb847-ba3a-4692-b7ff-b59aedcb2ed1" />

</p>
<p>
Install / Enable IIS in Windows WITH CGI-- Click start--> type control panel--> programs--> turn windows features on or off--> Internet information services--> world wide web services--> application development features--> check CGI and click ok and wait for it to finish installing. When we type in 127.0.0.1 in the web browser, Internet Information Services should appear. If we tried to type 127.0.0.1 before hand, it would have failed.
</p>
<br />

<p>
<img width="990" height="814" alt="Annotation 2025-08-31 023608" src="https://github.com/user-attachments/assets/6cd0ce16-2910-4a09-8fb2-43387960d2e7" />


</p>
<p>
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)-->click next--> click agree--> and yes to the next pop up and it should be installed 

</p>
<br />

<p>
<img width="984" height="772" alt="Annotation 2025-08-31 023746" src="https://github.com/user-attachments/assets/9c3a9447-07e1-45e2-97c9-d2d4888f2090" />

</p>
<p>
From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)--> check the box and click intsall--> say yes to the next pop up and the installation should be complete.

</p>
<br />

<p>
<img width="1490" height="738" alt="Annotation 2025-08-31 024023" src="https://github.com/user-attachments/assets/b4e745b1-7f71-4e62-992d-3999b8fe004d" />
<img width="1136" height="932" alt="Annotation 2025-08-31 024449" src="https://github.com/user-attachments/assets/3dfe92a2-7420-473c-8981-b36c1a421eb1" />

</p>
<p>
Create the directory C:\PHP--> right click file explorer on desktop (manilla folder)--> Windows (C:)--> right click and click new--> name it PHP
  
  From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder--> Go to the “osTicket-Installation-Files” folder and click php-7.3.8-nts-Win32-VC15-x86.zip--> right click and click extract all--> click browse--> go to Windows (C:)--> select the PHP folder we created--> click extract


</p>
<br />

<p>
<img width="960" height="592" alt="Annotation 2025-08-31 024811" src="https://github.com/user-attachments/assets/289ffd70-b388-4f11-92e1-3ac580e33a40" />

</p>
<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.--> double click VC_redist.x86.exe.--> check agree--> click intall and click yes to the pop up. Installation should be complete.

</p>
<br />

<p>
<img width="996" height="752" alt="Annotation 2025-08-31 025434" src="https://github.com/user-attachments/assets/bf388eea-8a61-464d-a575-2fddba143e44" />

</p>
<p>
From the “osTicket-Installation-Files” folder double click, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)--> click next--> check box and click next--> choose typical for setup and click install, say yes to pop up. 
  
  After, we are going to launch the MYDQL configuration wizard--> click finished and next and yes to the pop up and next again--> click standard configuration--> click next until you get the modify security settings--> DO NOT MESS THIS PART UP. For the sake of the tutorial, for the password type "root" both times--> click next and execute. Installation should be complete.

</p>
<br />

<p>
<img width="2126" height="1094" alt="Annotation 2025-08-31 031114" src="https://github.com/user-attachments/assets/2f1e9642-ca43-41ad-9235-5fa37e31841c" />
<img width="1804" height="1166" alt="Annotation 2025-08-31 031303" src="https://github.com/user-attachments/assets/a9d2ac0a-57fa-4f08-afd9-4d8581f2775e" />
<img width="1406" height="940" alt="Annotation 2025-08-31 031535" src="https://github.com/user-attachments/assets/cce9cf9a-83e9-4b93-b55a-edce08ef57eb" />
<img width="2128" height="1218" alt="Annotation 2025-08-31 031755" src="https://github.com/user-attachments/assets/ea0c50cb-444d-4bef-8125-ddb18ba502ec" />

</p>
<p>

Open IIS as an Admin--> Register PHP from within IIS (PHP Manager --> C:\PHP\php-cgi.exe)--> Reload IIS (Open IIS, Stop and Start the server)

Click start and type IIS and click run as admistrator--> Register PHP from within IIS, click PHP manager--> register a new PHP version--> click 3 dots to browse--> Windows (C:)--> PHP folder--> click php-cgi folder and click ok--> Reload IIS stop and start the server by either right clicking on the osTicket-vm tab on the left hand top corner or on the right hand side where it says server manager and click stop and then start.


</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

