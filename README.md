### SETUP ENV DOCKER LARAVEL
## Step 1: Setup and Check version docker installed
		docker --version
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/3.PNG)
## Step 2 : Clone project laravel version 5.8
		git clone https://github.com/phamminhanhdhbk/docker-laravel-mysql.git
## Step 3: Access to the project, create and edit file .env
        cd docker-laravel-mysql
        cp .env.example .env

        DB_CONNECTION=mysql
        DB_HOST=mariadb
        DB_PORT=3306
        DB_DATABASE=mydb
        DB_USERNAME=root
        DB_PASSWORD=root
       

 ![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/5.PNG)

## Step 4: run docker to create containers
		docker-compose up -d
        
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/2.PNG)
## Step 5: Attach to the php container to execute the command line
        docker exec -it  php bash 
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/7.PNG)
## Step 6:Update composer, Generate key, Update driver to mysql connect php
        composer install
        php artisan key:generate
        docker-php-ext-install pdo pdo_mysql
 ![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/8.PNG)
## Step 7: Set permission
        chown -R root:www-data storage/
        chmod -R 775 storage/
        chown -R root:www-data bootstrap/
        chmod -R 775 bootstrap/
## Step 8:Run migrate to create database tables
        php artisan migrate
## Step 9:Achievement
http://localhost:8696/ laravel
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/4.PNG)
# Step 10: Connect to mysql by Navicat
       
        host: localhost
        port: 3696
        user name : root
        password: root
        
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/1.PNG)
# Step 11: phpmyadmin
 http://localhost:4040/
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/6.png)
        
# Step 12: Reference documents
- https://viblo.asia/p/docker-compose-dung-moi-truong-cho-ung-dung-laravel-WrJvYEYJvVO
- https://docs.docker.com/docker-for-windows/install/
