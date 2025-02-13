## Backup and Restore PostgreSQL Database
```sh
sudo /Library/PostgreSQL/16/bin/pg_dump -U postgres -h localhost -d flowell -F p -f backup.sql
sudo /Library/PostgreSQL/16/bin/psql/createdb -U postgres -h localhost flowell
sudo /Library/PostgreSQL/16/bin/psql -U postgres -h localhost -d flowell -f backup.sql