# Instalation Web Server Linux-BIONIC

### linux Bionic 18.04

Install Apache2

    sudo apt install apache2 apache2-utils

Install Php:

    sudo add-apt-repository ppa:ondrej/php
    sudo apt-get update
    sudo apt-get install -y php5.6

Add Library:
    
    sudo apt-get install libapache2-mod-php5.6
    sudo apt-get install php5.6-pgsql
    sudo apt-get install php5.6-mcrypt
    sudo apt-get install php5.6-curl

Install PostgreSQL:

    sudo apt install postgresql postgresql-contrib
    
You can now start the database server using:

    /usr/lib/postgresql/10/bin/pg_ctl -D /var/lib/postgresql/10/main -l logfile start
    
Install Php 5.6:

    sudo apt-get install php5.6-xml
    sudo apt-get install php5.6-zip
    
Setting Up htaccess:

    sudo nano /etc/apache2/sites-available/000-default.conf

Add in <VirtualHost *:80>:

    <Directory /var/www/html>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Require all granted
    </Directory>
    
add mpdf:
  
    sudo apt-get install php5.6-mbstring

If Error 500, if your check link website and not allowed .htaccess in log apache2, use this:
  
    sudo a2enmod rewrite
    sudo service apache2 restart
    a2enmod rewrite
    systemctl restart apache2

Check:

    sudo php -v 
    sudo service apache2 status
    /usr/lib/postgresql/10/bin/postgres -V 
    sudo /etc/init.d/postgresql status
    
    
    
    
    
