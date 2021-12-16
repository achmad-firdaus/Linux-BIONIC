# Enter into the PostgreSql
    sudosu
    su - postgres
    psql

# Set Time Zone

Select Date NOW

    select now();
    show timezone;
    
Set Time Zone Temporary

    set timezone to 'Asia/Jakarta';
    
Set Time Zone Permanent

    /etc/postgresql/10/main# cat postgresql.conf
    
    Open postgresql.conf with nano editor
    Change Etc/GMT+7 for Indonesia
    
Check Type Time Zone
    
    select * from pg_timezone_names;


# Change password:
    ALTER USER postgres PASSWORD 'postgres';
