# TUNING APACHE SERVICE <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px">

#### LIST
- [Before Tuning TO Fast CGI (INFO) 👻](#before-tuning-)
- [Testing Ab Before Tuning 👻](#testing-ab-before-tuning-)
- [After Tuning TO Fast CGI (INFO) 👻](#after-tuning-)
- [Testing Ab After Tuning 👻](#testing-ab-after-tuning-)
- [How To Used FASTCGI👻](#how-to-used-fastcgi-)

#### BEFORE TUNING 👻

Php Info Original:
-Server Api still used apache
<p align="center">
  <img src="https://user-images.githubusercontent.com/77251566/147375288-27d9eed0-b928-4b99-ad95-1ca99ab60a2d.png">
</p>

#### TESTING AB BEFORE TUNING 👻

Test With Connection Internet:
<p align="center">
  <img src="https://user-images.githubusercontent.com/77251566/147375529-3d6478f1-6c96-40b7-82b0-33ed99f1c278.png">
</p>
This Is The Result Test of a Test That Failed:
<p align="center">
  <img src="https://user-images.githubusercontent.com/77251566/147375543-7658ea52-6989-43fb-99d2-4e5fad05e90b.png">
</p>
Test With NO Connection Internet The Result Test Stuck:
<p align="center">
  <img src="https://user-images.githubusercontent.com/77251566/147375489-d5e0dbf5-7eba-430e-bb9c-1d55d55c36db.png">
</p>

#### AFTER TUNING 👻

Php Info Original:
-Server Api have used FPM/FASTCGI
<p align="center">
  <img src="https://user-images.githubusercontent.com/77251566/147376281-a6ada314-9b19-4ecd-8407-4fe42e04d8b6.png">
</p>

#### TESTING AB AFTER TUNING 👻

Test With Connection Internet No Have Result Failed:
<p align="center">
  <img src="https://user-images.githubusercontent.com/77251566/147793701-9d9b767e-33f3-41f5-945d-7bae121eaa9e.png">
</p>

#### HOW TO USED FASTCGI 👻

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
    
