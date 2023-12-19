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
