# MySQL-docker-backup-restore
Backup, Restore MySQL Database from a Docker Container


# Docker container name list
docker ps -a

# Backup
docker exec [mysql_container_name] /usr/bin/mysqldump -u [mysql_username] --password=[mysql_password] [database_name] > backup.sql

# Restore
cat backup.sql | docker exec -i [mysql_container_name] /usr/bin/mysql -u [mysql_username] --password=[mysql_password] [database_name]
