# Linux-BIONIC
About all linux Bionic 18.04

# Instalation webserver

    Install Apache2(sudo apt install apache2 apache2-utils)

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

If Error 500 
  
    sudo a2enmod rewrite
    sudo service apache2 restart

if your check link website and not allowed .htaccess in log apache2, use this:
    
    a2enmod rewrite
    systemctl restart apache2

Check:

    sudo php -v 
    sudo service apache2 status
    /usr/lib/postgresql/10/bin/postgres -V 
    sudo /etc/init.d/postgresql status

This for change password db in psql:

    ALTER USER postgres PASSWORD 'postgres';

Set time zone postgres

    sudosu
    su - postgres
    psql
    select now();
    show timezone;
    set timezone to 'Asia/Jakarta';

Set time zone permanent

    /etc/postgresql/10/main# cat postgresql.conf

Untuk lihat jenis time:
    
    select * from pg_timezone_names;
    ubah postgresql.conf
    Etc/GMT+7


Set time zone server:

    date "+%H:%M:%S   %d/%m/%y"
    > 01:54:44   18/10/21

This for backup default time:
    
    sudo mv /etc/localtime /etc/localtime.orig

This for change time zone:
    
    sudo ln -sf /usr/share/zoneinfo/Asia/Jakarta /etc/localtime
    
    date
    >Mon Oct 18 08:57:41 WIB 2021



