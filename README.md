php 7.1.18, mysql 5.6, apache 2.4, phpmyadmin, composer

SETUP
1. update [PORTS], [CONTAINER_NAME] & [DB_NAME]" in /docker-compose.yml as required
2. update php version in /docker/apache_php/Dockerfile
3. update roots in /docker/apache_php/apache_config.conf
    1. DocumentRoot /var/www/project/[your_project_index_folder]/
    2. <Directory /var/www/project/[your_project_index_folder]/> 
4. update database version is /docker/db/Dockerfile
5. Then run "docker-compose up --build" and Your docker should be running fine now,
6. some examples of docker commands
    1. <code>docker exec -it [container_name] bash</code>
    2. <code>docker-compose exec [services] bash</code>
