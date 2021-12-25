
### Before

phpinfo:
![image](https://user-images.githubusercontent.com/77251566/147375288-27d9eed0-b928-4b99-ad95-1ca99ab60a2d.png)

apache version no have mpm:<br>
![image](https://user-images.githubusercontent.com/77251566/147375318-6e83e968-d6b2-4792-8dac-ee7b110d9129.png)

### TESTING AB

if have connection internet:
![image](https://user-images.githubusercontent.com/77251566/147375529-3d6478f1-6c96-40b7-82b0-33ed99f1c278.png)
![image](https://user-images.githubusercontent.com/77251566/147375543-7658ea52-6989-43fb-99d2-4e5fad05e90b.png)

if no have connection internet always disconected ping to server:
![image](https://user-images.githubusercontent.com/77251566/147375489-d5e0dbf5-7eba-430e-bb9c-1d55d55c36db.png)

### After
![image](https://user-images.githubusercontent.com/77251566/147376281-a6ada314-9b19-4ecd-8407-4fe42e04d8b6.png)


#HOW

Stop Apache2:

    sudo systemctl stop apache2

Disable Php:

    sudo a2dismod php5.6 or anything version php

Disable mpm prefork:

    sudo a2dismod mpm_prefork
    
Enable mpm event:

    sudo a2enmod mpm_event
    
Install FPM:

    sudo apt install php-fpm
    sudo apt install libapache2-mod-fcgid
    
Enable Fpm Php:

    sudo a2enconf php7.2-fpm
    
Enable Proxy:

    sudo a2enmod proxy
    sudo a2enmod proxy_fcgi
    
Restart Apache2:

    sudo systemctl restart apache2
    
