# postgres

## Connect to database
psql -h eu-north-1.rds.amazonaws.com -U postgres -W postgres </br>

## Create database
Change the user to postgres:</br>
`su - postgres`

Create User for Postgres</br>
`$ createuser testuser`

Create Database</br>
`$ createdb testdb`

Acces the postgres Shell:</br>
`psql ( enter the password for postgressql)`

Provide the privileges to the postgres user:</br>
```sh
alter user testuser with encrypted password 'qwerty';
grant all privileges on database testdb to testuser;
```

## Create dumb
psql -h eu-north-1.rds.amazonaws.com -U postgres -W postgres > dumper.sql </br>


sudo pg_dump --dbname=postgres://villages-dev:fusion@18.194.32.27/villages > dump-village-dev.sql</br>
sudo pg_dump postgresql://villages-dev:"password"@localhost:5432/villages > dumper.sql</br>
sudo pg_dump -U villages-dev -W villages > dumper.sql</br>

## Create database from dump
psql -U postgres [databasename] < dumper.sql</br>
psql -h villages.rds.amazonaws.com -U villages -W villages_db < dumper.sql</br>

OR
sudo -u postgres -i psql villages < dumper.sql


## Create MySQL dump
### Remote
mysqldump -h rds.host.name -u remote_user_name -p remote_db > dump.sql
### Local
mysql -u local_user_name -p local_db < dump.sql

