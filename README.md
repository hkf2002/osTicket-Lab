# osTicket-Lab
This is an osTicket Lab running on Windows 10 Pro. It will include the installation process and common issues that IT Help Desks receive.

# VM Environment

| Type | Specifications |
| ---- | ------------- |
|  OS  | Windows 10 Pro  |
| Memory  | 8192 MB  |
| Storage  | 50 GB  |
| Network |  NAT  |

# Enable IIS and Features

First step, is to enable IIS and its features. 

In order to enable IIS, navigate to the search bar and type in Windows Features and enable these features.

<img width="1265" height="909" alt="Screenshot 2026-06-20 213706" src="https://github.com/user-attachments/assets/b9bbccfa-991a-4275-ab1f-233987b80ac7" />

Once you have enabled those features you can check my going to your browser and typing in (http://localhost) where you should be met with this page.

<img width="1439" height="1065" alt="Screenshot 2026-06-20 213837" src="https://github.com/user-attachments/assets/828693f5-bd5c-4d8c-a330-88072fc9c9db" />

# PHP Manager, URL Rewrite and Visual C++

Now that the first step is complete, now you must install other dependencies IIS requires to run PHP.

Download [PHP Manager](https://github.com/RonaldCarter/PHPManager), [URL Rewrite Module](https://www.iis.net/downloads/microsoft/url-rewrite), and [Visual C++](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170).

<img width="1322" height="826" alt="Screenshot 2026-06-20 214122" src="https://github.com/user-attachments/assets/2b912387-4182-4688-9366-f5ee9a9e7427" />

<img width="578" height="149" alt="Screenshot 2026-06-20 214335" src="https://github.com/user-attachments/assets/4e0be5f9-4ef7-408e-ae89-7ebf03700b91" />

<img width="919" height="205" alt="Screenshot 2026-06-20 214350" src="https://github.com/user-attachments/assets/3ba12529-6630-42cb-83e2-97aef017e740" />

Now that you have downloaded them it's time to install them to your machine!

<img width="656" height="537" alt="Screenshot 2026-06-20 215254" src="https://github.com/user-attachments/assets/7b2f118b-f4f1-46d3-af0c-1b92292942ed" />

<img width="652" height="509" alt="Screenshot 2026-06-20 215312" src="https://github.com/user-attachments/assets/b0bc34e1-9088-4271-a17d-69b6ec507e29" />

<img width="614" height="373" alt="Screenshot 2026-06-20 215329" src="https://github.com/user-attachments/assets/a35da76c-38da-48b1-a42b-04ba50928c2c" />

# PHP & MySQL Installation

Now that all PHP dependencies are download you can finally download [PHP](https://www.php.net/downloads.php).

## Warning

***Make sure you download the Non-Threaded Safe Zip File or else non of this will work***

<img width="1207" height="610" alt="Screenshot 2026-06-21 114958" src="https://github.com/user-attachments/assets/d0119219-610b-40b1-8fb9-b0ca28720f55" />

Once downloaded, create a folder in the __C:__ Drive named PHP

<img width="636" height="81" alt="Screenshot 2026-06-20 215451" src="https://github.com/user-attachments/assets/88bd1108-fdb3-47cf-b720-51cd522094f6" />

Afterwards, extract PHP into the PHP folder you just created

<img width="815" height="601" alt="Screenshot 2026-06-20 215508" src="https://github.com/user-attachments/assets/83aed27e-e7ba-42de-a5b9-357da89949e7" />

Now install **[My SQL](https://dev.mysql.com/downloads/) Installer for Windows**

<img width="1580" height="794" alt="Screenshot 2026-06-21 120613" src="https://github.com/user-attachments/assets/64a81fc2-cfe2-4863-b0b2-7785a3ebbb15" />

After you have downloaded MySQL, run the installer, make sure the setup type is __Server Only__, create a root password, and Install as a __Windows Service__.

<img width="1150" height="858" alt="Screenshot 2026-06-20 222351" src="https://github.com/user-attachments/assets/d2488426-550a-428d-acf8-d82117005e7f" />

<img width="1123" height="854" alt="Screenshot 2026-06-20 222529" src="https://github.com/user-attachments/assets/61655f13-dc05-484c-a4b6-3675fb313a85" />

# Register PHP in IIS

Now it's time to register PHP in IIS.

Open IIS and navigate to PHP Manager

<img width="1325" height="868" alt="Screenshot 2026-06-20 215604" src="https://github.com/user-attachments/assets/d1d5cae3-1c60-4c58-862c-ecab51c3b488" />

Then you must register a new PHP version by navigating to **C:\PHP\php-cgi.exe**. 

After it has been registered, scroll down to extensions and enable the extensions I have enabled

<img width="352" height="397" alt="Screenshot 2026-06-21 113532" src="https://github.com/user-attachments/assets/52142d1e-3d8f-4310-8a21-6b96e2524684" />

Once they are all enabled navigate back to main screen and click **Restart** on the right pane.

# osTicket Installation and Database Creation

After all these steps you can now download osTicket and create the database.

Download [osTicket](https://github.com/osTicket/osTicket/releases/tag/v1.18.4).

<img width="1591" height="1002" alt="Screenshot 2026-06-20 220041" src="https://github.com/user-attachments/assets/bfcc2df6-51f5-4124-a872-39ddfbc97834" />

Extract the zip and then copy the contents of the **upload** folder and place those in the the following structure

***C:\inetpub\wwwroot\osTicket\***

<img width="1293" height="882" alt="image" src="https://github.com/user-attachments/assets/3c54554e-b3ff-4e51-8120-c5374608996c" />

## Important

**Make sure for the osTicket folder that you give full control to all users.**

<img width="1058" height="812" alt="Screenshot 2026-06-21 124023" src="https://github.com/user-attachments/assets/845d6ed4-4628-4c0d-a2f8-8d355b33d4af" />

Once permissions have been given navigate to the include folder and scroll down until you find a file called **ost-sampleconfig.php** and rename it to **ost-config.php**

<img width="166" height="59" alt="Screenshot 2026-06-20 221628" src="https://github.com/user-attachments/assets/da05594a-e196-45a4-bb6c-9ef663cf5a53" />

<img width="247" height="86" alt="Screenshot 2026-06-20 221640" src="https://github.com/user-attachments/assets/cd6518e8-6e92-42b0-b0c7-1607a66ce8d7" />

<img width="210" height="49" alt="Screenshot 2026-06-20 221705" src="https://github.com/user-attachments/assets/9beee2cc-64b0-4845-8c8f-e09b3fb8414d" />

Once those steps are done, navigate to the search bar and search for **MySQL 8.0 Command Line Client** and run as administrator.

Enter the root password you created during the installation process and run the commands 



