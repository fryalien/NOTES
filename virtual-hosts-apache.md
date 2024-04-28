YOUTUBE: https://youtu.be/7H-EgZa5giI

YOUTUBE: https://youtu.be/Z3DZUHIahsM

**Step 1 – Install Apache on Fedora 39**

First, you must run the system update and install Apache as your web server on Fedora 39. To do this, run the commands below:
```
sudo dnf update -y
```

```
sudo dnf install httpd -y
```

Next, start and enable the Apache service with the following commands:

```
sudo systemctl start httpd
```

```
sudo systemctl enable httpd
```

Also, you can check your Apache web server is active and running on Fedora 39:

```
sudo systemctl status httpd
```

**Step 2 – Configure PHP For WordPress on Fedora 39**

At this point, you must install PHP and some required extensions by using the following command:

```
sudo dnf install php php-fpm php-mysqlnd php-opcache php-gd php-xml php-mbstring php-curl php-pecl-imagick php-pecl-zip libzip -y
```

Verify your PHP installation by checking its version:

```
php --version
```

Now you must **edit the php.ini** file configuration and make some changes. To do this, you can open the file with your desired text editor like Vi editor or Nano editor:

```
sudo micro /etc/php.ini
```


Find the following lines in the file and make the following changes to them:
```
max_execution_time = 300
max_input_time = 300
memory_limit = 512M
post_max_size = 256M
upload_max_filesize = 256M
```

When you are done, save and close the file.

Next, start and enable PHP-FPM on Fedora 39 with the commands below:

```
sudo systemctl start php-fpm
```

```
sudo systemctl enable php-fpm
```

You can verify your PHP-FPM is active and running with the command below:

```
sudo systemctl status php-fpm
```

**Step 3 – MariaDB Configuration For WordPress on Fedora 39**

At this point, you must install MariaDB as your database engine for WordPress and create a database and user. To install MariaDB, run the command below:

```
sudo dnf install mariadb-server -y
```

Then, start and enable the MariaDB service with the following commands:

```
sudo systemctl start mariadb
```

```
sudo systemctl enable mariadb
```

Verify your MariaDB service is active and running on Fedora 39:

```
sudo systemctl status mariadb
```

**At this point, you must run the MariaDB security script:**

```
sudo mysql_secure_installation
```

You will be asked to **change the root password** for MariaDB and **enter Y for other questions**.

Now log in to your MariaDB shell with your configured password:

# CREATE NEW DATABASE

```
sudo mariadb -u root -p
```

**IN MariaDB**

```
CREATE DATABASE jupiterdb;
```

```
CREATE DATABASE marsdb;
```

```
GRANT ALL PRIVILEGES ON jupiterdb.* TO 'jupuser' IDENTIFIED BY '12345';
```

```
GRANT ALL PRIVILEGES ON marsdb.* TO 'marsuser' IDENTIFIED BY '12345';
```

```
FLUSH PRIVILEGES;
```

```
EXIT;
```

# CREATE NEW FOLDER

```
sudo mkdir -p /var/www/html/jupiter
```

```
sudo mkdir -p /var/www/html/mars
```

# JUPITER SITE

```
cd /var/www/html/jupiter
```

```
sudo wget https://www.wordpress.org/latest.tar.gz
```

```
sudo tar -xvf latest.tar.gz
```

```
cd wordpress
```

```
sudo cp wp-config-sample.php wp-config.php
```

```
sudo micro wp-config.php
```

In the file, you must define your database settings as shown below:

**The name of the database for WordPress**

define( 'DB_NAME', '**jupiterdb**' );

**Database username**

define ('DB_USER', '**jupuser**');

**Database password**

define( 'DB_PASSWORD', '**12345**' );

**Database hostname**

define( 'DB_HOST', '**localhost**' );

When you are done, save and close the file.


**Now you must set the correct ownership and permission for the WordPress directory**

```
sudo chown -R apache:apache /var/www/html/jupiter/wordpress
```

```
sudo chmod -R 755 /var/www/html/jupiter/wordpress
```


# MARS SITE

```
cd /var/www/html/mars
```

```
sudo wget https://www.wordpress.org/latest.tar.gz
```

```
sudo tar -xvf latest.tar.gz
```

```
cd wordpress
```

```
sudo cp wp-config-sample.php wp-config.php
```

```
sudo micro wp-config.php
```

In the file, you must define your database settings as shown below:

**The name of the database for WordPress**

define( 'DB_NAME', '**marsdb**' );

**Database username**

define ('DB_USER', '**marsuser**');

**Database password**

define( 'DB_PASSWORD', '**12345**' );

**Database hostname**

define( 'DB_HOST', '**localhost**' );

When you are done, save and close the file.


**Now you must set the correct ownership and permission for the WordPress directory**

```
sudo chown -R apache:apache /var/www/html/mars/wordpress
```

```
sudo chmod -R 755 /var/www/html/mars/wordpress
```


# ADD NEW VIRTUAL HOST

```
sudo micro /etc/httpd/conf.d/wp.conf
```

Add the following content with your domain name to the file:

```
<VirtualHost 127.0.0.1:80>
    ServerName www.jupiter.com
    DocumentRoot /var/www/html/jupiter/wordpress
    <Directory /var/www/html/jupiter/wordpress>
        Allowoverride all
    </Directory>
</VirtualHost>
```

```
<VirtualHost 127.0.0.1:80>
    ServerName www.mars.com
    DocumentRoot /var/www/html/mars/wordpress
    <Directory /var/www/html/mars/wordpress>
        Allowoverride all
    </Directory>
</VirtualHost>
```

When you are done, save and close the file.

# ADD VIRTUAL SITES TO CONFIG
```
micro /etc/httpd/conf/httpd.conf
```

```
<VirtualHost 127.0.0.1:80>  
    DocumentRoot /var/www/html/jupiter
    ServerName www.jupiter.com
</VirtualHost>  
  
<VirtualHost 127.0.0.1:80>  
    DocumentRoot /var/www/html/mars
    ServerName www.mars.com
</VirtualHost>
```

**ADD HOSTS TO YOUR HOSTS FILE**

```
micro /etc/hosts
```

```
www.mars.com www.jupiter.com
```

Next, restart the Apache service to apply the changes:

```
sudo systemctl restart httpd
```

# INSTALL WORDPRESS VIA WEB INTERFACE for JUPITER

```
http://www.jupiter.com
```

In the first screen, you must provide your WordPress site name and define an admin user and password for it. Then, click on Install WordPress.

```
jupiter
```

```
12345
```

```
jupiter@local.com
```

**LOG IN**
```
http://www.jupiter.com/wp-admin/
```

# INSTALL WORDPRESS VIA WEB INTERFACE for MARS

```
http://www.mars.com
```

In the first screen, you must provide your WordPress site name and define an admin user and password for it. Then, click on Install WordPress.

```
mars
```

```
12345
```

```
mars@local.com
```

**LOG IN**
```
http://www.mars.com/wp-admin/
```

