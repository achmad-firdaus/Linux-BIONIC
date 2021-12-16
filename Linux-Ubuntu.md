# Set time zone server

Check your date

    date "+%H:%M:%S   %d/%m/%y"
    > 01:54:44   18/10/21
    
First backup configuration Origin
  
    sudo mv /etc/localtime /etc/localtime.orig

Change Time Zone Asia Jakarta
    
    sudo ln -sf /usr/share/zoneinfo/Asia/Jakarta /etc/localtime
    
    date
    >Mon Oct 18 08:57:41 WIB 2021
    
    
    
    
    
