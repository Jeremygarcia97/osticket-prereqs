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

- Connect to your Virtual Machine with Remote Desktop
- Install / Enable IIS in Windows
- Install Web Platform Installer
- Install osTicket 
- Download and Install HeidiSQL
- Created database for "osTicket
- Clean up
- Change File Permissions

<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/3c954155-947e-4880-a0b3-1ce32735e112)

<p>
Create our virtual machine by going to azure portal and by clicking create vm. Once you click create new vm we need to configure some details first. First create a new resourse group, next put a name for the virutal machine then select a region and then for the image section choose windows 10.
</p>
<br />

![image](https://github.com/user-attachments/assets/a9463b67-e414-4a09-9252-dfc01f9ff8e5)

<p>
Next create a username and password that you will remember, click the box at the bottom left conner and then hit review + create.
</p>
<br />

![image](https://github.com/user-attachments/assets/85da74ac-6159-4f0d-8a78-58a86fb9a3fb)

<p>
  In order to remote desktop into our virtual machine we first need to get the public IP address, then we go to our local search bar on our computer we search for remote desktop. We enter the public IP address from our virtual machine, enter the username and password and click connect.
</p>
<br />

![image](https://github.com/user-attachments/assets/d0b070f1-8751-4940-852a-116c0fb60f20)

<p>
When you remote desktop into you virtual machine. We have to Install / Enable IIS in Windows, First go into the start menu in the vm and type "control panel" and then click programs.
</p>
<br />

![image](https://github.com/user-attachments/assets/4f38f495-041e-43a3-b677-8e8fa4326975)

<p>
once your the windows for program, on the left side of that window click were it says "turn windows feature on or off". Another small window will appear scroll down till you see "internet information services" check the box, then you will check where it says "world wide web services" and finally click where it says CGI and then click OK and will intsall web server.   
</p>
<br />

![image](https://github.com/user-attachments/assets/cfdf87cb-1703-4337-985a-ab8d9c9213c2)

<p>
Go back into osTicket-installation file and start downloading PHP manager file.
</p>
<br />

![image](https://github.com/user-attachments/assets/cd0470f0-09d9-4d0f-b616-2a55c77e79a0)

<p>
With in the same folder you will start downloading the Rewrite module software.
</p>

![image](https://github.com/user-attachments/assets/bd1b1aeb-f5d0-4786-a31c-17d0912bfb8c)

<p>.
Now you will create a directory C;\PHP, Which means you will go to the C drive on the file explore a create a new folder called PHP.
</p>
<br />

![image](https://github.com/user-attachments/assets/b8bf6fea-8cc8-4ded-a965-f18e6f533677)

<p>
Now going back to the osTicket folder, we will unzip the other php file into the C drive folder called PHP that we had created in the last step.
</p>

![image](https://github.com/user-attachments/assets/79011b02-77c5-4988-ade7-6ebc92c66098)

<p>
Install the VC_redist file.
</p>
<br />

![image](https://github.com/user-attachments/assets/fee72573-8a8d-4989-997e-c61c1affc118)
![image](https://github.com/user-attachments/assets/8d1ce3dc-c533-48f9-a348-b9f150a4e2dd)


<p>
Next we will install mysql 5.5.62. which is the database for osticket.
Follow these directions to install mysql.
1. start downloading the file
2. click finish
3. click Standard confiuguration
4. create a username and password. For lab purposes only use the word "root" for the username and password.
5. click on finish
</p>
<br />

![image](https://github.com/user-attachments/assets/71135b7f-736b-4cb9-b45c-776bb8bb0a06)
![image](https://github.com/user-attachments/assets/8e0bc36f-86f4-4584-b26c-d12c13d9e507)


<p>
 - 1. Search for Internet Information Services (IIS) and select Open as admin. 2. then go to PHP mananger, 3. click register new version, 4 browse the C drive, 5. click the PHP folder, 6. within the PHP folder double click folder call php-cgi, 7. click OK, 8. Reload IIS by clicking stop then start on the right side below where it says "actions", 

.
</p>
<br />


![image](https://github.com/user-attachments/assets/cf331396-1d75-400f-9602-3fff4520939d)
![image](https://github.com/user-attachments/assets/ad8fb900-a371-49a3-933f-322099685a4c)
![image](https://github.com/user-attachments/assets/e3f42867-5d60-4ca1-8418-3a03d0f6855a)


<p>
Now time to install osTicket v1.15.8. First stet go back to osTicket folder, 2 now inside the folder highlight the file called osTicket and we are going to exctract the file, once its done exctracting it will create a new file with the same name, click that new file.3 Go to the C drive click folder called inetpub then wwwroot.4 We are going to copy the upload folder into wwwroot. 5 then rename the upload folder to "osTicket" do not mess this up.
</p>
<br />

![image](https://github.com/user-attachments/assets/3043efc2-514d-4f2a-a4ee-f506a88e3b86)

<p>
Inside IIs manager you will reload IIS again (open IIS, stop and start the server). Next you will click sites then default then osTicket (those are on the left side of IIS manager) then you will click "browse .80" (that is on the right side). you will open osticket installer but some extension are missing but we will take care of it in the next step.
</p>
<br />

![image](https://github.com/user-attachments/assets/6d196055-c76f-401a-a29c-b18b70601278)
![image](https://github.com/user-attachments/assets/4aaa8efe-393e-4f9e-aee1-f5f9b9389211)
![image](https://github.com/user-attachments/assets/687d91cd-e104-4bca-90c8-f07feec41355)
![image](https://github.com/user-attachments/assets/cb2dc565-a01b-4987-a4b6-85b698761a6f)


<p>
Go into IIS manager again, click the osTicket folder and then click PHP manager, click enable or disable extension. Look for the extensions called (php_imad.ll,php_intl.dll,php_opcache.dll). Go back to the osTicket that on web browser and refreash the page to check in extension were enabled.
</p>
<br />

![image](https://github.com/user-attachments/assets/c6610d7e-257a-4623-8580-97e6d368bda1)
![image](https://github.com/user-attachments/assets/c31af7aa-77d9-4446-8aa4-8cff225a1620)


<p>
Open Windows Explorer and select C: > inetpub > wwwroot > osTicket > include. Then look for the file call ost-sampleconfig.php then rename it to ost-config.php.
</p>
<br />

![image](https://github.com/user-attachments/assets/a332d78e-3eb3-4892-9a7c-0c24e8664dc8)


<p>
Right-click ost-config.php. Open Properties > Security > Advanced > Permissions. Select Disable Inheritance > Remove all inherited permissions from this object. Select Disable Inheritance > Remove all inherited permissions from this object. Allow everyone full control (check all boxes) > Select apply > OK
</p>
<br />

![image](https://github.com/user-attachments/assets/b08fa77b-a2e5-427b-9509-5168501da9f0)

<p>
Go back to browser and start filling out information. System user and admin user email must be different it can not be the same. 
</p>
<br />

![image](https://github.com/user-attachments/assets/6e1277be-625b-4128-ac7d-b99dbd4d71b8)



<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

![image](https://github.com/user-attachments/assets/316a8f02-467d-4995-a9bc-858bc333adac)

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
