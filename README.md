# SwolKout-Workout-Tracker
SwolKout is a free and open source web application that helps you track your workouts.

# Installation

**Recommended installation: via Docker**

1. Install Docker on your machine.
2. Run the command: 

``` docker run -d -p 8876:80 yeettkds/swolkout:1.0 ```

Now you should be able to access the web application at: http://localhost:8876


**Local installation**

1. Install the necessary services:

```sudo apt install apache2 mariadb-server mysql-common php php-mysqli libapache2-mod-php -y```

2. Clone the repostitory
3. Copy the website code into ```/var/www/html```

```sudo cp -r SwolKout-Workout-Tracker/src/html /var/www/html```

4. Give the proper permissions to ```exerciselist.txt```

```sudo chmod +w /var/www/html/exerciselist.txt```

5. Clone [PHPMailer](https://github.com/PHPMailer/PHPMailer.git) into the website folder

```git clone https://github.com/PHPMailer/PHPMailer.git /var/www/html```

5. Start mysql

```mysqld_safe &```

7. Set the password and the privileges for the user ```root```
```
mysql -u root -e "SET PASSWORD FOR 'root'@'localhost' = PASSWORD('12345');"
mysql -u root -e "GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '12345' WITH GRANT OPTION;"
mysql -u root -e "FLUSH PRIVILEGES;"
```
- ATTENTION: if you set another password for root make sure to update ```/var/www/html/database.php``` with the modified password.
8. Import the database
```
mysql -u root -e "CREATE DATABASE IF NOT EXISTS swolkout;"
mysql -u root -p12350 swolkout < ./SwolKout-Workout-Tracker/database/swolkout.sql
```
- ATTENTION: if you set another password for root make sure to change ```-p12350``` with ```-p[your_password]```

Now you should be able to access the web application at: http://localhost


**Important notes after installation**
- the default admin login credentials are:
   - email: ```admin@example.com```
   - password: ```password```
