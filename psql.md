# Things to write SQL with Postgres

## Connect
```bash
sudo --login --user=postgres psql

# OR
sudo -u postgres psql

#OR connect to db
psql -h <host> -U <username> -d <database>
```

## Chnage password
```bash
sudo -u postgres psql -c "ALTER USER postgres PASSWORD '<new-password>';"
```

## CONF
```
/etc/postgresql/14/main/pg_hba.conf
```

*Create DB
createdb db_name</br>
`sudo -u postgres createdb db_name`

To login without a password:</br>
`sudo -u user_name psql db_name`

To reset the password if you have forgotten:</br>
`ALTER USER user_name WITH PASSWORD 'new_password';`

*Go to CLI</br>
`psql postgres`

*Show databases</br>
`\dt+;`

### Quit
```psql
quit

/q
```


## Crete user using bash and sql

```bash
sudo -u postgres psql
postgres=# create database mydb;
postgres=# create user myuser with encrypted password 'mypass';
postgres=# grant all privileges on database mydb to myuser;
```

```bash
sudo -u vadymhavrylenko createuser postgres
sudo -u vadymhavrylenko createdb copilot
```

```sql
CREATE DATABASE yourdbname;
CREATE USER youruser WITH ENCRYPTED PASSWORD 'yourpass';
GRANT ALL PRIVILEGES ON DATABASE yourdbname TO youruser;
```

### Grant permissions to a user
```sql
-- Grant permissions on the public schema
GRANT USAGE ON SCHEMA public TO your_username;
GRANT CREATE ON SCHEMA public TO my_user;

-- Grant select, insert, update, delete on all tables in the public schema
GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA public TO your_username;

-- If you want to grant permissions on future tables as well
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT SELECT, INSERT, UPDATE, DELETE ON TABLES TO your_username;
```



