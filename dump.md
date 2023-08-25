# postgres

## Connect to database
`psql -h eu-north-1.rds.amazonaws.com -U postgres -W postgres`

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
```sh
psql -h eu-north-1.rds.amazonaws.com -U postgres -W postgres > dumper.sql


sudo pg_dump --dbname=postgres://villages-dev:"password"@18.194.32.27/villages > dump-village-dev.sql
sudo pg_dump postgresql://villages-dev:"password"@localhost:5432/villages > dumper.sql
sudo pg_dump -U villages-dev -W villages > dumper.sql
```

## Create database from dump
```sh
psql -U postgres [databasename] < dumper.sql
psql -h villages.rds.amazonaws.com -U villages -W villages_db < dumper.sql

# OR
sudo -u postgres -i psql villages < dumper.sql
```

## Create MySQL dump
### Remote
```sh
mysqldump -h rds.host.name -u remote_user_name -p remote_db > dump.sql
```
### Local
```sh
mysql -u local_user_name -p local_db < dump.sql
```

