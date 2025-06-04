**WORDPRESS ON UBUNUTU 24.04.2-LTS WITH NGINX AND MARIADB**

---

>Update your system.

```
sudo apt update && sudo apt upgrade -y
```

>Install `nginx`.

```
sudo apt install nginx -y
```

>Check the status.

```
systemctl status nginx.service
```

>Install `php`.

```
sudo apt install php-fpm php-common php-mysql php-xml php-snmp php-intl php-curl php-gd php-imagick php-cli php-dev php-imap php-mbstring php-opcache php-redis php-soap php-zip -y
```

---

>Install `MariaDB`.

```
sudo apt install mariadb-server -y
```

```
sudo systemctl start mariadb
```

```
sudo systemctl enable mariadb
```

```
systemctl status mariadb
```

```
sudo mysql_secure_installation
```

```
sudo mariadb -u root
```

```
CREATE DATABASE wpdb;
```

```
CREATE USER 'wpuser'@'localhost' IDENTIFIED BY '12345';
```

```
GRANT ALL PRIVILEGES ON wpdb.* TO 'wpuser'@'localhost';
```

```
FLUSH PRIVILEGES;
```

```
EXIT;
```

---

>Install `WordPress`.

```
cd /var/www/html
```

```
sudo wget https://wordpress.org/latest.zip
```

```
sudo unzip latest.zip
```

```
sudo rm latest.zip
```

```
sudo mv wordpress/* .
```

```
sudo rmdir wordpress/
```

---

>Configure WP.

```
sudo cp /var/www/html/wp-config-sample.php /var/www/html/wp-config.php
```

```
sudo micro /var/www/html/wp-config.php
```

>In the file, you must define your database settings as shown below:

**The name of the database for WordPress**

define( 'DB_NAME', '**wpdb**' );

**Database username**

define ('DB_USER', '**wpuser**');

**Database password**

define( 'DB_PASSWORD', '**12345**' );

Database hostname

define( 'DB_HOST', 'localhost' );

>When you are done, save and close the file.

```
sudo chown -R www-data:www-data /var/www/html
```

```
sudo chmod -R 755 /var/www/html
```

---

>Configure virtual host.

```
sudo micro /etc/nginx/sites-available/default
```

>Delete everything in the file and just enter this:

```
server {
    listen 80;
    server_name wplocal;
    root /var/www/html;
    index index.php;
    server_tokens off;
    access_log /var/log/nginx/wordpress_access.log;
    error_log /var/log/nginx/wordpress_error.log;
    client_max_body_size 64M;

    location / {
        try_files $uri $uri/ /index.php?$args;
    }

    location ~ \.php$ {
        fastcgi_pass unix:/run/php/php-fpm.sock;
        fastcgi_index index.php;
        include fastcgi_params;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include /etc/nginx/fastcgi.conf;
    }
}

```

```
sudo nginx -t
```

```
sudo systemctl restart nginx.service
```

---

>Go to your browser to this page:

```
http://wplocal.localhost
```

>Install WordPress.

>User here can be different from the one form the database.