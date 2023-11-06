# Things to write SQL with Postgres

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
