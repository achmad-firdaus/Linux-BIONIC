# LINUX UBUNTU <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px">

#### LIST
- [Set time zone server 👻](#set-time-zone-server-)
- [Crontab 👻](#crontab-)

#### SET TIME ZONE SERVER 👻

Check your date

    date "+%H:%M:%S   %d/%m/%y"
    > 01:54:44   18/10/21
    
First backup configuration Origin
  
    sudo mv /etc/localtime /etc/localtime.orig

Change Time Zone Asia Jakarta
    
    sudo ln -sf /usr/share/zoneinfo/Asia/Jakarta /etc/localtime
    
    date
    >Mon Oct 18 08:57:41 WIB 2021
    
#### CRONTAB 👻

Check crontab

    crontab -l

Edit crontab

    crontab -e
    
Remove all crontab

    crontab -r


    
    
    
