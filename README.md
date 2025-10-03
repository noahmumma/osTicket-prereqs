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

- Item 1: Log into Azure VM using RDP and within the VM, download [osTicket Installation Files](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and unzip it onto your desktop (if you do not know how to create an Azure VM, check out my other tutorial!)
- Item 2: Within Control Panel, install/enable IIS in Windows WITH CGI
- Item 3: From "osTicket-Installation-Files", install "PHP Manager" for IIS, then install the "Rewrite Module"
- Item 4: Create the directory, "C:\PHP", and unzip "PHP 7.3.8" into the "C:\PHP" folder
- Item 5: From "osTicket-Installation-Files", install "VC_redist" and "MySQL" with typical setup, standard configuration, and a username and password YOU WILL NOT FORGET
- Item 6: Open Internet Information Services (IIS) as an admin, and register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
- Item 7: Stop and start the IIS server, and begin the installation of osTicket

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/brvxSkn.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
If you are here, congratulations! You have completed all the prerequisites for installing osTicket. Now, all that is left is installation and setup. Navigate to "osTicket-Installation-Files", and unzip "osTicket-v1.15.8.zip". Once completed, extract the "upload" folder into “c:\inetpub\wwwroot”. Then, rename the "upload" folder to "osTicket". Finally, stop and start the IIS server. 
</p>
<br />

<p>
<img src="https://i.imgur.com/f76qUzG.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now, in the IIS server, navigate to "Sites" --> "Default Sites" --> "osTicket". Click "Browse .80", which will open osTicket! 
</p>
<br />

<p>
<img src="https://i.imgur.com/W2fMAde.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, in IIS, head to osTicket's PHP extensions, and enable "php_imap.dll", "php_intl.dll", and "php_opcache.dll". Refresh osTicket to ensure the changes went through. These allow for more features while using osTicket. Then, within File Explorer, rename "C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php" to "C:\inetpub\wwwroot\osTicket\include\ost-config.php". Finally, click continue on the osTicket browser and fill out the text boxes with your information (Note: the "default email" will be the one receiving emails from customers).
</p>
<br />

<p>
<img src="https://i.imgur.com/5GnDBqJ.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now you need a specific database for osTicket and provide the credentials for it in the osTicket "Database Settings" section. For this, head back into "osTicket-Installation-Files" and install "HeidiSQL". Boot up HeidiSQL after it has successfully installed, and select "+ new". The user and password for this should be the same that you entered when installing "MySQL." Finally, right-click, "Unnamed" --> "Create new" --> "Database", then name it "osTicket". After you select "ok", head back to the osTicket Installer browser and enter the information you just created for your SQL database. Click "Install", and congratulations! You have successfully installed osTicket!
</p>
<br />
