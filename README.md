### SETUP ENV DOCKER LARAVEL
## Step 1: Install docker if you haven't already
## Step 2: Check version installed
		docker --version
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/3.PNG)
## Step 3 : Clone project laravel version 5.8
		git clone https://github.com/phamminhanhdhbk/docker-laravel-mysql.git
## Step 4: 
        cd docker-laravel-mysql
## Step 5: Create file .env
        cp .env.example .env
## Step 6: Edit file .env
        ```
        DB_CONNECTION=mysql
        DB_HOST=mariadb
        DB_PORT=3306
        DB_DATABASE=mydb
        DB_USERNAME=root
        DB_PASSWORD=root
        ```
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/5.PNG)

## Step 7: Run docker
		docker-compose up -d
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/2.PNG)
## Step 8: Attach to container php
        docker exec -it  php bash 
## Step 9:Update composer
        composer install
## Step 10: Generate key
        php artisan key:generate
## Step 11: Update driver to mysql connect php
        docker-php-ext-install pdo pdo_mysql
## Step 12: Set permission
        chown -R root:www-data storage/
        chmod -R 775 storage/
        chown -R root:www-data bootstrap/
        chmod -R 775 bootstrap/
## Step 13:Run migrate
        php artisan migrate
## Step 14:Result
http://localhost:8696/ laravel
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/4.PNG)
# Step 15: Connect to mysql by Navicat
        ```
        host: localhost
        port: 3696
        user name : root
        password: root
        ```
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/1.PNG)
# Step 16: phpmyadmin
 http://localhost:4040/
![alt text](https://github.com/phamminhanhdhbk/docker-laravel-mysql/blob/master/public/images/readme/6.png)
        
# Step 17: Reference documents
- https://viblo.asia/p/docker-compose-dung-moi-truong-cho-ung-dung-laravel-WrJvYEYJvVO
- https://docs.docker.com/docker-for-windows/install/
