# Install-Apache-PHP-MySQL-TEST

## To install Apache on *Windows*
1. [Download the files](https://www.apachelounge.com/)
2. Extract the ZIP file to the root of the C:/
3. Configure Apache 
   - Line 60 : Listen *:80
   - Line 162: LoadModule rewrite_module modules/mod_rewrite.so
   - Line 227: ServerName localhost:80
   - Line 234: AllowOverride All *allow .htaccess overrides*
4. Change the Web Page Root (optional)
   - Line 251: DocumentRoot "YourDrive:/YourFolder"
   - Line 252:<Directory "D:/WebPages">
5. Test your Installation
   ```
   # navigate to Apache bin directory
   cd /Apache24/bin
   # Test httpd.conf validity
   httpd -t
   ```
6. Install Apache as a Windows service
   ```
   cd /Apache24/bin
   httpd -k install
   ```
**Source:** [How to install Apache on Windows](https://www.sitepoint.com/how-to-install-apache-on-windows/)
## To install PHP on *Windows* 
1. [Download the PHP files](https://www.php.net/downloads.php)
   - Thread safe version
2. Create a new php folder in the root of your C:\ drive and extract the contents of the ZIP into it.
3. Configure php.ini
   - PHP’s configuration file is named php.ini. This doesn’t exist initially, so copy C:\php\php.ini-development to C:\php\php.ini. This default configuration provides a development setup which reports all PHP errors and warnings.
   - In most cases, you’ll need to remove a leading semicolon (;) to uncomment a setting.
   ```
   extension=curl
   extension=gd
   extension=mbstring
   extension=pdo_mysql
   ```
   ```
   [mail function]
   ; For Win32 only.
   ;http://php.net/smtp
   SMTP = mail.myisp.com
   ; http://php.net/smtp-port
   smtp_port = 25

   ; For Win32 only.
   ; http://php.net/sendmail-from
   sendmail_from = my@emailaddress.com
   ```
4. Add C:\php to the path environment variable
5. Configure PHP as an Apache module
   - Ensure Apache isn’t running and open its C:\Apache24\conf\httpd.conf
   - Add the following lines to the bottom of the file to set PHP as an Apache module
   ```
   # PHP8 module
   PHPIniDir "C:/php"
   LoadModule php_module "C:/php/php8apache2_4.dll"
   AddType application/x-httpd-php .php
   ```
   - Optionally, change the DirectoryIndex setting to load index.php instead of index.html when it can be found.
   ```
   <IfModule dir_module>
    DirectoryIndex index.php index.html
   </IfModule>
   ```
   - test the updates from a cmd command line
   ```
   cd C:\Apache24\bin
   httpd -t
   ```
   - Syntax OK should appear <br>



**Source:** [How to install PHP on Windows](https://www.sitepoint.com/how-to-install-php-on-windows/)
## To install MySQL on *Windows* 
1. [Download MSI installer](https://dev.mysql.com/downloads/windows/installer/)
2. [Use this link to install it properly](https://phoenixnap.com/kb/install-mysql-on-windows)


There are also some other ways to install MySQL which you can find out about them through the link below: <br>
[How to install MySQL](https://www.sitepoint.com/how-to-install-mysql/)
   