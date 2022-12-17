# XAMPP Web Server

### Apache configuration file: 
/Applications/XAMPP/xamppfiles/etc/httpd.conf,
/Applications/XAMPP/xamppfiles/etc/extra/httpd-xampp.conf

### PHP configuration file:
/Applications/XAMPP/xamppfiles/etc/php.ini
### MySQL configuration file:
/Applications/XAMPP/xamppfiles/etc/my.cnf
### ProFTPD configuration file:
/Applications/XAMPP/xamppfiles/etc/proftpd.conf
### PhpMyAdmin configuration file:
/Applications/XAMPP/xamppfiles/phpmyadmin/config.inc.php

### Run xampp services by command line

To start apache service
sudo /Applications/XAMPP/xamppfiles/bin/apachectl start

To start mysql service
sudo /Applications/XAMPP/xamppfiles/bin/mysql.server start

To stop Apache web server, enter:
sudo apachectl stop

To start Apache web server again, enter:
sudo apachectl start

To restart apache web server, enter:
sudo apachectl restart

To run a configuration file syntax test
sudo apachectl configtest

To reload apache web server after editing the config file
First edit the config file, run:
$ sudo vi /etc/apache2/httpd.conf

Make changes as per your needs. Close and save the file. To reload new changes, run:
sudo apachectl graceful

### Troubleshooting via the Terminal

Step 1, Find the PID (process ID) via the terminal, 
such as _mysql  13722

print all processes owned by all users
ps ax | grep mysql
user       31450    grep mysql
_mysql     13722

print all processes owned by a user named "x"
ps aux | grep mysql
(g/re/p -- globally search for a regular expression and print matching lines)

Step 2, kill the PID

sudo kill -pid

### In Terminal, launch the following command:

### sudo /Applications/XAMPP/xamppfiles/xampp

Usage: xampp <action>

start Start XAMPP (Apache, MySQL and eventually others)
startapache Start only Apache
startmysql Start only MySQL
startftp Start only ProFTPD

stop Stop XAMPP (Apache, MySQL and eventually others)
stopapache Stop only Apache
stopmysql Stop only MySQL
stopftp Stop only ProFTPD

reload Reload XAMPP (Apache, MySQL and eventually others)
reloadapache Reload only Apache
reloadmysql Reload only MySQL
reloadftp Reload only ProFTPD

restart Stop and start XAMPP
security Check XAMPP's security

enablessl Enable SSL support for Apache
disablessl Disable SSL support for Apache

backup Make backup file of your XAMPP config, log and data files

oci8 Enable the oci8 extenssion

fix_rights Resets file permissions

##Virtual Host (Server Directives)
<VirtualHost *:80>
    DocumentRoot “/Users/username/Project/"
    ServerName 127.0.0.1
	ServerAlias localhost
</VirtualHost>
<VirtualHost *:80>
    DocumentRoot "/Applications/XAMPP/xamppfiles/htdocs/"
	ServerName xampp.localhost
  <Directory  "Applications/XAMPP/xamppfiles/htdocs/">
	AllowOverride All
   Require all granted
   Options Indexes FollowSymLinks
	</Directory>
</VirtualHost>

** Please Note the directory directives might need to be adjusted for your system **
