# MySQL-docker-backup-restore
Backup, Restore MySQL Database from a Docker Container


# Docker container name list
docker ps -a

## Backup
docker exec [mysql_container_name] /usr/bin/mysqldump -u [mysql_username] --password=[mysql_password] [database_name] > backup.sql

## Restore
cat backup.sql | docker exec -i [mysql_container_name] /usr/bin/mysql -u [mysql_username] --password=[mysql_password] [database_name]


# MySQL or Maria 
## Backup
docker exec [db_container_name] mysqldump -u [mysql_username] --password=[mysql_password] [database_name] > /desired/path/to/db.dump

## Restore
docker exec -i [db_container_name] mysql -u [mysql_username] --password=[mysql_password] [database_name] < /path/to/db.dump
