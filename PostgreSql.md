# POSTGRESQL <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px">

#### LIST
- [Enter into the PostgreSql 👻](#enter-into-the-postgresql-)
- [Set Time Zone 👻](#set-time-zone-)
- [Change password 👻](#change-password-)
- [Backup 👻](#backup-)
- [Restore 👻](#restore-)

#### ENTER INTO THE POSTGRESQL 👻
    sudosu
    su - postgres 
        exit (if you want exit)
    psql
        \q (if you want exit)

#### SET TIME ZONE 👻

- Select Date NOW

        select now();
        show timezone;
    
- Set Time Zone Temporary

        set timezone to 'Asia/Jakarta';
    
- Set Time Zone Permanent

        /etc/postgresql/10/main# cat postgresql.conf

        Open postgresql.conf with nano editor
        Change Etc/GMT+7 for Indonesia
    
- Check Type Time Zone
    
        select * from pg_timezone_names;


#### CHANGE PASSWORD 👻
    ALTER USER postgres PASSWORD 'postgres';

#### BACKUP 👻
    pg_dump <DATABASE NAME> > <DIRECTORY AND FILENAME>.sql
    
#### RESTORE 👻
    psql <DATABASE NAME> < <DIRECTORY AND FILENAME>.sql
