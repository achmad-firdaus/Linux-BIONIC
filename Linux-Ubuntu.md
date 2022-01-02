# LINUX UBUNTU <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px">

#### LIST
- [Set time zone server 👻](#set-time-zone-server-)
- [Crontab 👻](#crontab-)
- [Create 👻](#create-)
- [Zip 👻](#zip-)
- [Permission 👻](#permission-)
- [Change Ownership 👻](#change-ownership-)
- [Remove 👻](#remove-)
- [Watch Performance 👻](#watch-performance-)
- [Watch Ram 👻](#watch-ram-)

#### SET TIME ZONE SERVER 👻

- Check your date:

        date "+%H:%M:%S   %d/%m/%y"
        > 01:54:44   18/10/21
    
- First backup configuration Origin:
  
        sudo mv /etc/localtime /etc/localtime.orig

- Change Time Zone Asia Jakarta:
    
        sudo ln -sf /usr/share/zoneinfo/Asia/Jakarta /etc/localtime

        date
        >Mon Oct 18 08:57:41 WIB 2021

- Check status:

        timedatectl status

- Set Time Zone automatically disabled:
  
        timedatectl set-ntp 0

- Set Time Zone automatically enabled:
  
        timedatectl set-ntp 1
    
#### CRONTAB 👻

- Check crontab:

        crontab -l

- Edit crontab:

        crontab -e
    
- Remove all crontab:

        crontab -r
        
#### CREATE 👻

- Folder:

        mkdir <folder name>
    
- File:

        touch <folder name>

#### ZIP 👻

- Zip all:

        zip -r <zip name>.zip <folder/file name>

- Unzip:

        unzip <zip name>.zip

#### PERMISSION 👻

- Permission all in:

        chmod -R 777 <folder/file name> or chmod -R 775 <folder/file name>

#### CHANGE OWNERSHIP 👻

- Change owner folder:

        sudo chown <username> <folder name>

#### REMOVE 👻

- Folder & File:

        rm -r <folder/file name> 
        
#### WATCH PERFORMANCE 👻

- If you don't have htop, you must install befor used 'htop' command :

        sudo apt install htop
        htop

#### WATCH RAM 👻

- Delay 1 second:

        watch -n 1 free -m
        
        
