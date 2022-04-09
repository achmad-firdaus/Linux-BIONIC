# POSTGRESQL <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px">

#### LIST
- [Enter into the PostgreSql 👻](#enter-into-the-postgresql-)
- [Set Time Zone 👻](#set-time-zone-)
- [Change password 👻](#change-password-)
- [Backup 👻](#backup-)
- [Restore 👻](#restore-)
- [Error 👻](#error-)

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
    
#### ERROR 👻
    Case Error:
    if you enter in sudo su - postgres, then psql:
        psql: error: could not connect to server: No such file or directory
        Is the server running locally and accepting
        connections on Unix domain socket "/var/run/postgresql/.s.PGSQL.5432"?
    SOLVE:
    1. Check status postgresql
        systemctl status postgresql@12-main.service
        
            ● postgresql@12-main.service - PostgreSQL Cluster 12-main
                 Loaded: loaded (/lib/systemd/system/postgresql@.service; enabled-runtime; vendor preset: enabled)
                 Active: failed (Result: protocol) since Sat 2022-04-09 06:52:23 WIB; 19s ago
                Process: 494339 ExecStart=/usr/bin/pg_ctlcluster --skip-systemctl-redirect 12-main start (code=exited, status=1/FAILURE)

            Apr 09 06:52:23 achmad-Latitude-7480 systemd[1]: Starting PostgreSQL Cluster 12-main...
            Apr 09 06:52:23 achmad-Latitude-7480 postgresql@12-main[494339]: Error: /usr/lib/postgresql/12/bin/pg_ctl /usr/lib/postgresql/12/bin/pg_ctl start -D /var/lib/postgresql/12/main -l /var>
            Apr 09 06:52:23 achmad-Latitude-7480 postgresql@12-main[494339]: 2022-04-09 06:52:23.382 WIB [494357] FATAL:  data directory "/var/lib/postgresql/12/main" has invalid permissions
            Apr 09 06:52:23 achmad-Latitude-7480 postgresql@12-main[494339]: 2022-04-09 06:52:23.382 WIB [494357] DETAIL:  Permissions should be u=rwx (0700) or u=rwx,g=rx (0750).
            Apr 09 06:52:23 achmad-Latitude-7480 postgresql@12-main[494339]: pg_ctl: could not start server
            Apr 09 06:52:23 achmad-Latitude-7480 postgresql@12-main[494339]: Examine the log output.
            Apr 09 06:52:23 achmad-Latitude-7480 systemd[1]: postgresql@12-main.service: Can't open PID file /run/postgresql/12-main.pid (yet?) after start: Operation not permitted
            Apr 09 06:52:23 achmad-Latitude-7480 systemd[1]: postgresql@12-main.service: Failed with result 'protocol'.
            Apr 09 06:52:23 achmad-Latitude-7480 systemd[1]: Failed to start PostgreSQL Cluster 12-main.
            
     2. permission deny, you can use chmod 700 in folder mainmain
     3. restart your postgres and check again
     
     if you want create new claster, like this:
     1. check: pg_lsclusters
     2. sudo pg_ctlcluster 12 main start
     3. restart your postgres and check again
