<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10 Pro</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8

<h2>Installation Steps</h2>

@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

body {
  font-family: 'Roboto', sans-serif;
}

  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url(https://fonts.gstatic.com/s/roboto/v32/KFOmCnqEu92Fr1Mu72xKOzY.woff2) format('woff2');
  unicode-range: U+0460-052F, U+1C80-1C8A, U+20B4, U+2DE0-2DFF, U+A640-A69F, U+FE2E-FE2F;

1.) Begin by creating a virtual machine by visiting <a href="https://portal.azure.com/">Azure Portal</a>. Configure the virtual machine with Windows 10 Pro, version 22H2. Ensure the setup includes at least 2 vCPUs and 16 GB of memory.

2.) After creating your virtual machine, connect to it using its assigned public IP address. Use the Remote Desktop Connection app to establish the connection.

</p>
<br />

<p>
<img src= "https://imgur.com/WjoGqAV.png" height="50%" width="50%"/>
</p>
<p>
<p>
<img src="https://imgur.com/Zf2jw07.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
3.) After connecting to your virtual machine, navigate to the Control Panel. Open the "Programs" section and select "Turn Windows features on or off." Additionally, ensure you extract the osTicket installation files to prepare for the next steps.

<p>
<img src="https://imgur.com/hE8q3jM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/VCdqbhc.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/LBGkAw6.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
4.) Enable IIS (Internet Information Services) in Windows, including the CGI and Common HTTP Features components:

Navigate to World Wide Web Services → Application Development Features and select:

[X] CGI
[X] Common HTTP Features
  
<p>
<img src="https://imgur.com/hUtlnuI.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/pbPeHb1.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Ensure that all "Common HTTP Features" options are selected.
 

To verify that IIS is installed and enabled, open a web browser of your choice and navigate to 127.0.0.1. 
You should see a page that looks similar to this: 
  
<p>
<img src="https://imgur.com/QV7x6mb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
  
  
5.) With IIS now enabled, proceed to download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the installation files. Follow the steps in the installation wizard to complete the process.
  
6.) Next, download and install the Rewrite Module (rewrite_amd64_en-US.msi) from the installation files. Follow the installation wizard to complete the setup.
  
7.) Create a folder named PHP in the C: drive.
  
8.) Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) from the installation files, then extract its contents into the C:\PHP folder.
  
  
  **ATTENTION**
  
If a warning or prompt appears during the download process, select “Keep” to retain the file.
<p>
<img src="https://imgur.com/xZv1Yhw.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/YwBhqo0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

9.) After extracting the ZIP file into the C:\PHP folder, proceed to download and install VC_redist.x86.exe from the installation files. Follow the setup wizard to complete the installation.
  
10.) Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi). Then follow these steps in the setup wizard:

- Select Typical Setup
- After the installation, launch the Configuration Wizard.
- Choose Standard Configuration in the wizard.
- When prompted, set the new root password to Password1.
  
<p>
<img src="https://imgur.com/Y5a64cE.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Proceed to execute the steps outlined on the next page to complete the process.
  
<p>
<img src="https://imgur.com/pf11l6i.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
11.) Now that the files are downloaded and installed, search for IIS in the Windows search bar and open Internet Information Services (IIS) Manager as an administrator. The program should appear with a window similar to this:
  
<p>
<img src="https://imgur.com/rgdZwmM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
12.) Now, to register PHP within IIS, follow these steps:

In the IIS Manager, click on PHP Manager in the left-hand pane.
From there, you can manage PHP settings and register PHP with IIS.
  
<p>
<img src="https://imgur.com/k8TMbOu.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Register new version of PHP.
  
<p>
<img src="https://imgur.com/DAXaUNV.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
To provide the path to the PHP executable file (php-cgi.exe), follow these steps:

- In the PHP Manager in IIS, click on the option to register PHP.
- Navigate to C:\PHP.
- Select the php-cgi.exe file and click OK to register it.
  
<p>
<img src="https://imgur.com/oJZ0gp9.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Restart IIS server.
  
<p>
<img src="https://imgur.com/AtYkdl1.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
13.) To install osTicket v1.15.8, follow these steps:

- Download osTicket from the Installation Files folder.
- Extract the contents of the downloaded file.
- Copy the "upload" folder to C:\inetpub\wwwroot.
- Navigate to C:\inetpub\wwwroot, then rename the "upload" folder to "osTicket".
- Afterward, reload IIS to apply the changes.

This will set up osTicket on your IIS server.
  
14.) In IIS, follow these steps:

- Go to Sites in the left pane.
- Expand Default and select osTicket.
- On the right-hand side, click *Browse :80.
- This will open osTicket in your default web browser for further configuration.
  
<p>
<img src="https://imgur.com/AlLIIgU.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Some extensions are not enabled on the osTicket browser.
  
<p>
<img src="https://imgur.com/aYr2g27.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  To enable the extensions:
  -Go back to IIS, sites -> Default -> osTicket
  -Double click PHP manager
  -Click "Enable or disable an extension"
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/uigyKjb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  We will want to enable three extensions from here.
  
  1.) php_imap.dll
 
  2.) php_intl.dll
  
  3.) php_opcache.dll
  
<p>
<img src="https://imgur.com/TQE9X9w.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
15.) After enabling the required extensions in IIS, the next step is to rename a file in the osTicket folder:

- Open File Explorer and navigate to C:\inetpub\wwwroot\osTicket\include.
- Search for ost-sampleconfig.php.
- Rename ost-sampleconfig.php to ost-config.php.

Once the file is renamed, follow these steps:

- Right-click on the file and select Properties.
- In the Properties window, go to the Security tab.
- Click on Advanced, then disable Inheritance.
- Select Remove all inherited permissions from this object.
  
Now, we'll add new permissions:

- Click Add to proceed.
  
<p>
<img src="https://imgur.com/VPZvOdo.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Select a principal
  
<p>
<img src="https://imgur.com/PoGk34d.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
 Type "Everyone" in the box.
  
<p>
<img src="https://imgur.com/BmPDwvH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Make sure Full Control and all the other boxes are checked.
  
<p>
<img src="https://imgur.com/vdzLyBu.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Click Apply and Ok.
  
<p>
<img src="https://imgur.com/saRO3y5.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
 Once the file permissions are set, continue with the osTicket setup in the browser:

- On the osTicket browser page, click Continue.
- Fill out the required fields on the page, but leave the Database Settings at the bottom for now—we'll address that shortly.
- Next, download and install HeidiSQL from the Installation Files to manage your database.
  
<p>
<img src="https://imgur.com/i7a4gWC.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  When the program is open we will create a new session in it.
  
<p>
<img src="https://imgur.com/g5M1i61.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  We want to make sure the username is root and the password is Password1.
  
<p>
<img src="https://imgur.com/LEAZNOc.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
After connecting to HeidiSQL, return to the osTicket setup in the browser to complete the configuration:

In the Database Settings section of the browser, enter the following details:
- Username: root
- Password: Password1
  
Next, follow these steps to create the new database in HeidiSQL:
- In HeidiSQL, right-click on "Unnamed" on the left side.
- Select Create new and then Database.
- Name the new database osTicket.
- Once the database is created, return to the osTicket browser page and under MySQL Database, enter osTicket.
  
<p>
<img src="https://imgur.com/0rG1AJm.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
The final step is to perform some cleanup:

Delete the setup folder:
- Navigate to C:\inetpub\wwwroot\osTicket\setup and delete the setup folder.
- Only delete the setup folder—nothing else.

Reset file permissions:
- After deleting the setup folder, go back to the ost-config.php file and set its permissions back to Read-only. This will secure the configuration file.
  
<p>
<img src="https://imgur.com/wFr0pkK.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/jsJOPyn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
The final step is to log in to osTicket through your web browser:

- Open your browser and go to the osTicket login page.
- Use the admin credentials you set up during the installation to log in and complete the setup process.
  
<p>
<img src="https://imgur.com/uHVdDsx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Congratulations! You have now successfully installed and set up osTicket! 🎉
