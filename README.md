# postgres_commands
Installation of PostgreSQL and common commands

Install [PostgreSQL](https://www.postgresql.org).
Use termimal.
```
cd C:\Program Files\PostgreSQL\13\bin
```

To set internet access to PostgreSQL use the following command:
```
netsh advfirewall firewall add rule name="Postgre Port" dir=in action=allow protocol=TCP localport=5432
```

To change to russian codding use the following command:
```
chcp 1251
```

To check the version use the following command:
```
psql –V
```

To create new database use the following command:
``` 
createdb -U postgres testdb
```

To get the list of databases use the following command:
```
psql -U postgres –l
```

To create new user use the following command:
```
createuser -U postgres operator
alter user operator with encrypted password 'password'
``` 

To create database for another user:
```
createdb -U postgres -O operator baseSQL
```

To run psql (shell):
```
psql –U postgres
```

To enter any database:
```
psql db_name user_name
```
or if the db_name is the same with user
``` 
psql -U operator 
```

To set role for user use SQL commands:
```
postgres=# ALTER ROLE operator SUPERUSER CREATEROLE CREATEDB;
```

To set privileges to concrete database:
```
postgres=# GRANT ALL privileges on database testdb to operator 
```

To get the list of users with roles use the following command:
```
postgres=# \du
```

To create schema by any name :
```
postgres=# CREATE SCHEMA schema_name
```

To create schema as user name:
```
postgres=# CREATE SCHEMA AUTHORIZATION operator;
```

To get the list of schemas use the following command:
```
postgres=# \dn
```
