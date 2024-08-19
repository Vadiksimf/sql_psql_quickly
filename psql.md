# Things to write SQL with Postgres

## Connect
```bash
sudo --login --user=postgres psql

# OR
sudo -u postgres psql
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
