
A PHP SCRIPT TO UPGRADE FROM KOHANA 3.2.X TO KOHANA 3.3.X
------------------------------------------------------

Based on the works of :  
=> Daan (http://stackoverflow.com/users/987864/daan)
http://stackoverflow.com/questions/13935621/how-to-upgrade-from-kohana-3-2-to-3-3-implementing-psr-0  
=> Alex Cartwright <alexc223@gmail.com>
https://github.com/AlexC/kohana-upgrade-script

This script is designed to do bulk changes to your codebase that can
easily be automated, changes that would otherwise have the potential
to take a very long time for a large project. It does not provide a
fully automated migration, and it is highly recommended that you read
the official Kohana 3.3 upgrade guide before running this script.
http://kohanaframework.org/3.3/guide/kohana/upgrading

------------------------------------------------------

Be smart, be safe :
BACKUP YOUR WEBSITE BEFORE RUNNING THIS SCRIPT
------------------------------------------------------

This script handles :
- Changes in Boostrap / database config file / auth config file
- PSR-0 support (file/class naming conventions)
	- Change the file names 
	- Change the name of class in all files  (including calls, extends...)
- Case sensitive ORM, HTTP, URL, UTF8, HTML classes
- New syntax for Browser cache checking
- New syntax for Redirects (HTTP 300, 301, 302, 303, 307)
- Apply the changes listed above in Modules too

This script does not handle :
- HTTP Exceptions
- Custom Error Pages (HTTP 500, 404, 403, 401 etc)
- Query Builder Identifier Escaping
- Route Filters

Things to do :
- improve regex to prevent replacement mistakes between class and functions

HOW TO USE
------------------------------------------------------

This script is to use on your local version of your website
Do not use on your production server (as you will experiment permission issues as your server is not supose to let you modify PHP files dynamically for security reasons)
Once your local site is updated and you test everything, upload files via FTP to your production server. 

1/ Backup your site

2/ Download kohana 3.3

3/ Manulay replace the following folders from Kohana 3.3 to the website to upgrade :
- system
- modules/auth
- modules/cache
- modules/codebench
- modules/database
- modules/image
- modules/minion
- modules/orm
- modules/unittest
- modules/userguide

4/ Edit the settings at the begining of the script 

5/ Run this file
   - if you use a Mac : the best way will be to open the php file with BBedit and chose in the '#!' menu "Run in Terminal"  
   - you can also open a Terminal, go to the script folder and type ./upgrade-kohana.php  
   - you can also just run the script from your local webserver http://localhost/website/upgrade-kohana.php but it's not recommended as you may have some permissions problem to modify the PHP files  

------------------------------------------------------

AUTHOR
------------------------------------------------------

@author Erwan Dupeux-Maire  
www.upyupy.fr  
www.bwat.fr 