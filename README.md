# Install-Apache-PHP-MySQL-TEST

## To install Apache on *Windows*
1. [Download the files](https://www.apachelounge.com/)
2. Extract the ZIP file to the root of the C:/
3. Configure Apache 
   - Line 60 : Listen *:80
   - Line 162: LoadModule rewrite_module modules/mod_rewrite.so
   - Line 227: ServerName localhost:80
   - Line 224: AllowOverride All *allow .htaccess overrides*
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