# Postgres

- `.psqlrc` (see [https://www.digitalocean.com/community/tutorials/how-to-customize-the-postgresql-prompt-with-psqlrc-on-ubuntu-14-04](https://www.digitalocean.com/community/tutorials/how-to-customize-the-postgresql-prompt-with-psqlrc-on-ubuntu-14-04):


```
\set PROMPT1 '%M:%> %n@%/%R%#%x '
\set PROMPT2 '%M %n@%/%R %# '
\x auto
```

## SQL

- Extract as CSV:
`\copy (select(first_name, last_name from users where created > '2019-01-01')) to '/Users/ghelouis/users.csv' CSV`

- Import from CSV:
`\copy users(first_name, last_name) from '/Users/ghelouis/users.csv' CSV`

- Transaction:
```
begin transaction;
update users set first_name = 'toto' where id = '123';
update users set first_name = 'tutu' where id = '124';
update users set first_name = 'titi' where id = '125';
commit transaction;
```

## PSQL

```
\l           # list databases
\c my_db     # connect to db
\dt          # show tables
\d TABLE     # show table definition
\dy          # show triggers
\df          # list functions
\du          # list roles
\e           # edit command using $EDITOR
\x           # activate pretty print
```
