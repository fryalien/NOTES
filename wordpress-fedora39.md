SOURCE: https://orcacore.com/wordpress-installation-fedora39/

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

```
sudo mariadb -u root -p
```

From your MariaDB shell, run the following commands to create a database and user with all privileges for WordPress on Fedora 39:

```
MariaDB [(none)]> CREATE DATABASE wordpressdb;
```
```
MariaDB [(none)]> GRANT ALL PRIVILEGES ON wordpressdb.* TO 'wpuser'@'localhost' IDENTIFIED BY '12345';
```

Then, **flush the privileges** and exit from MariaDB:

```
MariaDB [(none)]> FLUSH PRIVILEGES;
```
```
MariaDB [(none)]> EXIT;
```


**Step 4 – Download and Configure Latest WordPress on Fedora 39**

At this point, you must navigate to your Apache web root directory on Feodra 39 with the command below:

```
cd /var/www/html
```

Then, use the following wget command to download the latest tar.gz package of WordPress:

```
sudo wget https://www.wordpress.org/latest.tar.gz
```

When your download is completed, extract your file with the command below:

```
sudo tar -xvf latest.tar.gz
```

Next, switch to your WordPress directory:

```
cd wordpress
```

At this point, you must rename the default WordPress configuration file with the command below:

```
sudo cp wp-config-sample.php wp-config.php
```

Then, open the file with your desired text editor:

```
sudo micro wp-config.php
```

In the file, you must define your database settings as shown below:

**The name of the database for WordPress**

define( 'DB_NAME', '**wordpressdb**' );

**Database username**

define ('DB_USER', '**wpuser**');

**Database password**

define( 'DB_PASSWORD', '**12345**' );

**Database hostname**

define( 'DB_HOST', '**localhost**' );

When you are done, save and close the file.

Now you must set the correct ownership and permission for the WordPress directory on Fedora 39:

```
sudo chown -R apache:apache /var/www/html/wordpress
```
```
sudo chmod -R 755 /var/www/html/wordpress
```


**Step 5 – Configure Apache Virtual Host File For WordPress**

At this point, you must create an Apache virtual host file to serve WordPress. To do this, you can run the following command:

```
sudo micro /etc/httpd/conf.d/wp.conf
```

Add the following content with your domain name to the file:

```
<VirtualHost *:80>
    ServerAdmin admin@example.com
    ServerName wplocal
    DocumentRoot /var/www/html/wordpress
    <Directory /var/www/html/wordpress>
        Allowoverride all
    </Directory>
</VirtualHost>
```

When you are done, save and close the file.

Next, restart the Apache service to apply the changes:

```
sudo systemctl restart httpd
```

**Step 6 – Firewalld Configuration for WordPress**

Here we assumed that you have enabled FirewallD. Now you need to allow ports 80 and 443 through your firewalld on Fedora 39. To do this, run the commands below:

```
sudo firewall-cmd --permanent --zone=public --add-service=http
```
```
sudo firewall-cmd --permanent --zone=public --add-service=https
```

Then, reload the firewall to apply the new rules:

```
sudo systemctl reload firewalld
```

**Step 7 – Install WordPress via Web Interface in Fedora 39**

At this point, you can continue your WordPress installation and access your dashboard by typing your domain name in your web browser:

**http://wplocal.localhost**

In the first screen, you must provide your WordPress site name and define an admin user and password for it. Then, click on Install WordPress.

**WP-DATA FOR INSTALLATION**

SITE: WP-LOCAL

wpuser

12345

wpuser@local.com

**LOG IN**
```
http://wplocal.localhost/wp-admin/
```


**no cert part, STEP 8**



**THE END**



**PLUGINS**

All-in-one WP Migration !!!!

GUIDE: https://www.youtube.com/watch?v=VaNxAJ0sZZ4

PLUGIN: https://chinedudigital.com/all-in-one-wp-migration-import-stuck/
