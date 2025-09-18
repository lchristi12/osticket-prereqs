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
  
  From the “osTicket-Installation-Files” folder--> unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder--> Go to the “osTicket-Installation-Files” folder and click php-7.3.8-nts-Win32-VC15-x86.zip--> right click and click extract all--> click browse--> go to Windows (C:)--> select the PHP folder we created--> click extract


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
<img width="680" height="526" alt="Screenshot 2025-08-30 225226" src="https://github.com/user-attachments/assets/a537f816-b476-43c0-8f0c-704b368a8d3c" />

</p>
<p>
From the “osTicket-Installation-Files” folder double click, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)--> click next--> check box and click next--> choose typical for setup and click install, say yes to pop up. 
  
  After, we are going to launch the MYSQL configuration wizard--> click finished and next and yes to the pop up and next again--> click standard configuration--> click next until you get the modify security settings--> DO NOT MESS THIS PART UP. For the sake of the tutorial, for the password type "root" both times--> click next and execute. Installation should be complete.

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
<img width="1132" height="940" alt="Annotation 2025-08-31 032011" src="https://github.com/user-attachments/assets/c5def4fd-443c-41cd-b216-c317cb802c72" />
<img width="2048" height="1528" alt="Annotation 2025-08-31 032604" src="https://github.com/user-attachments/assets/78c44a35-20f4-4f3d-8319-7e4d803abd4f" />
<img width="1746" height="714" alt="Annotation 2025-08-31 032814" src="https://github.com/user-attachments/assets/1e6d0578-141f-4e1e-ad5f-b5591a7ba90f" />

</p>
<p>
Install osTicket v1.15.8--> From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”

Right click osTicket-v1.15.8.zip and click extract all and click extract, wait until it is finished--> open the osTicket-v1.15.8 in the osTicket-Installation-Files folder and there should be 2 folders, scripts and upload

Copy the “upload” folder into “c:\inetpub\wwwroot”--> Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”--> right click file explorer--> Windows (C:)--> inetpub--> wwwroot--> copy and drag the upload folder from osTicket-v1.15.8 into the wwwroot and rename it to osTicket exactly by by right clicking and click rename--> After, go back to IIS to stop and start the server like we did perviously


</p>
<br />

<p>
<img width="2126" height="1214" alt="Annotation 2025-08-31 033244" src="https://github.com/user-attachments/assets/cbd67085-fa2a-4fae-a09d-43b7796c328e" />
<img width="1318" height="1212" alt="Annotation 2025-08-31 033414" src="https://github.com/user-attachments/assets/d0ddcc78-c412-4750-b9f7-7490fabca2d5" />


</p>
<p>
Next we are going to attempt to load the OS Ticket site--> On IIS manager, go to sites--> default--> osTicket--> click on "browse" on the right hand side and the OS Ticket site should appear in the web browser.
</p>
<br />

<p>

<img width="2108" height="1522" alt="Annotation 2025-08-31 034156" src="https://github.com/user-attachments/assets/0f99b293-ff44-4ec3-8041-96609d6518d8" />
<img width="1308" height="1144" alt="Annotation 2025-08-31 034356" src="https://github.com/user-attachments/assets/7de44245-3bff-494a-b45a-74d7a2ede03a" />

 
</p>
<p>
Note that some extensions are not enabled--> On IIS manager, go to sites--> default--> osTicket--> PHP manager--> click on enable or disable an extention--> enable the following extensions: php_imap.dll, php_intl.dll, and php_opcache.dll--> Refresh the osTicket site in your browser, observe the changes.
</p>
<br />

<p>
<img width="1700" height="1324" alt="Annotation 2025-08-31 034943" src="https://github.com/user-attachments/assets/4dcc8f45-3b82-46af-b38d-082322b631f4" />

</p>
<p>
Rename: ost-config.php--> Windows C:--> inetpub--> wwwroot--> osTicket--> include--> ost-sampleconfig.php, rename this to ost-config.php (DO NO MESS THIS PART UP)

</p>
<br />

<p>
<img width="1526" height="996" alt="Annotation 2025-08-31 035200" src="https://github.com/user-attachments/assets/d16ad08a-85ce-40c0-91d5-753611138cf8" />

</p>
<p>
Assign Permissions: ost-config.php--> right click, properties--> security--> advanced--> disable inheritance--> remove all inherited permissions from this object.
</p>
<br />

<p>
<img width="1702" height="998" alt="Annotation 2025-08-31 035551" src="https://github.com/user-attachments/assets/10afac63-096e-4ab7-858b-ea01e469548d" />

</p>
<p>
Next we are going to add new permissions--> select a principle--> for the sake of this tutorial, type "everyone" in the box and click ok--> check full control and click okay--> Click apply and ok
</p>
<br />

<p>
<img width="822" height="1220" alt="Annotation 2025-08-31 035826" src="https://github.com/user-attachments/assets/95f5986c-3026-4360-831a-f56cecb5300e" />

</p>
<p>
Go back to the OS Ticket site and click continue--> fill in the information--> Helpdesk name, create a name--> type a random email for the sake of the tutorial--> Username, lets use adminuser and password, Password1 for this tutorial--> next install HeidiSQL
</p>
<br />

<p>
<img width="1192" height="886" alt="Annotation 2025-08-31 040331" src="https://github.com/user-attachments/assets/cf8523d9-47ef-47fc-8a4f-d9afb97e7d6e" />

</p>
<p>
From the “osTicket-Installation-Files” folder--> download HeidiSQL, https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe--> click agree and click next until you get to the install button and click install and when it is done, click finish.
</p>
<br />

<p>
<img width="1372" height="960" alt="Annotation 2025-08-31 040644" src="https://github.com/user-attachments/assets/9e76252f-c2a6-46d5-8b04-b72dc315c5da" />

</p>
<p>
Next we are going to set up a database for OS Ticket, HeidiSQL should be opened--> click new--> user root, password, root from earlier on and click open
</p>
<br />

<p>
<img width="2094" height="1182" alt="Annotation 2025-08-31 041008" src="https://github.com/user-attachments/assets/d5bd7db1-fd3f-46a5-9513-1b619c5023df" />

</p>
<p>
Creating a database--> right click unnamed--> create new--> databased--> Type for the name, osTicket exactly--> click ok and the database has been created.
</p>
<br />

<p>
<img width="556" height="370" alt="Annotation 2025-08-31 041211" src="https://github.com/user-attachments/assets/6b1238c7-ef35-40d4-af8c-9321922e85c3" />

</p>
<p>
Finish setting up OS Ticket--> MySQL database, type osTicket--> username, root--> password, root--> click install now.
</p>
<br />

<p>
<img width="1098" height="848" alt="Annotation 2025-08-31 041323" src="https://github.com/user-attachments/assets/37431c56-2f57-4188-a13f-3b06d5b66e9c" />

</p>
<p>
You have successfully installed OS Ticket. This is the end of the tutorial and I hope you found this helpful. Do not delete the VM because there are more activities to do for the next parts. Turn off the VM if you are not using it so you do not get charged.
