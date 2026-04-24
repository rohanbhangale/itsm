###### ***INSTALLATION***

1.Download XAMPP: Go to the official site and download XAMPP.



2.Start Services: Install XAMPP, then open the XAMPP Control Panel and click "Start" for both Apache and MySQL.



3.Download MediaWiki: Go to the official MediaWiki website and download the latest.zip file.



4.Extract the Files: Extract the contents of that zip file into this exact folder path on your computer: C:\\xampp\\htdocs\\mediawiki.



5.Inside, you will see the actual mediawiki-1.45.1 folder. Copy that folder.



6.Now, navigate to your XAMPP web root directory, which is usually located at C:\\xampp\\htdocs\\.



7.Paste the folder you copied into the htdocs folder.



8.Right-click the newly pasted folder and Rename it to simply mediawiki. (This ensures it matches the URL you are trying to visit).



###### ***CONFIG***

1.Open the XAMPP Control Panel.In the Apache row, click the Config button.From the drop-down menu, click on PHP (php.ini). 2.This will open a text file in your default text editor (like Notepad).

3.Press Ctrl + F to open the search tool and find this exact line: ;extension=intl.

4.Delete the semicolon (;) at the very beginning of that line. 



1.In the XAMPP Control Panel, click the Config button next to MySQL and select my.ini.

2.Press Ctrl + F and search for 3306.

3.Change every instance of 3306 to 3307.



1.Open File Explorer and go to C:\\xampp\\phpMyAdmin.

2.Find the file named config.inc.php and open it with Notepad (or VS Code).

3.Press Ctrl + F and search for 127.0.0.1. You should find a line that looks like this:

$cfg\['Servers']\[$i]\['host'] = '127.0.0.1';

4.Create a new line right below it and paste this exactly:

$cfg\['Servers']\[$i]\['port'] = '3307';

Save the file (Ctrl + S) and close it.




***SETUP***
---

1. Open a new browser tab and go to http://localhost/phpmyadmin.
2. Click New and create a database named mediawiki\_db

###### 

1. Open a new tab and go to your wiki installer: http://localhost/mediawiki/mw-config.
2. Choose your language and click Continue until you reach the "Connect to database" page.
3. Important: In the "Database host" field, change it from localhost to 127.0.0.1:3307 (this tells it to use your new port).
4. Fill in the rest of the details as per your manual:
5. Database name: mediawiki\_db 
6. Database username: root 
7. Database password: (Leave this completely blank)



1. On the next pages, give your Wiki a name.
2. Create your administrator account by entering a username (like admin) and a strong password.
3. Keep clicking Continue (you can leave the other settings as default for now) until the installation finishes.
4. Once done, the setup will automatically download a file named LocalSettings.php.
5. Move that downloaded LocalSettings.php file directly into your C:\\xampp\\htdocs\\mediawiki\\ folder.
6. Open the file located at C:\\xampp\\htdocs\\mediawiki\\LocalSettings.php, paste these exact lines at the bottom of the file:
7. $wgGroupPermissions\['\*']\['edit'] = false; $wgGroupPermissions\['user']\['edit'] = true; 



