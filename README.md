# php 7.1.18
# mysql 5.6
# apache 2.4
# phpmyadmin

# SETUP
# 1.  update ports in /docker-compose.yml as required
# 2.  update php version in /docker/apache_php/Dockerfile
# 3.  update roots in /docker/apache_php/apache_config.conf
# 3.1 DocumentRoot /var/www/project/[your_project_index_folder]/
# 3.2 <Directory /var/www/project/[your_project_index_folder]/>
# 4.  update database version is /docker/db/Dockerfile
