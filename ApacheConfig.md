


# SSL Localhost

- sudo a2enmod ssl
- sudo mkdir -p /etc/ssl/localcerts
- sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
-keyout /etc/ssl/localcerts/apache-selfsigned.key \
-out /etc/ssl/localcerts/apache-selfsigned.crt \
-subj "/C=US/ST=State/L=City/O=Organization/CN=localhost"


<VirtualHost *:443>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html

    SSLEngine on
    SSLCertificateFile /etc/ssl/localcerts/apache-selfsigned.crt
    SSLCertificateKeyFile /etc/ssl/localcerts/apache-selfsigned.key

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

- sudo a2ensite localhost-ssl

Breakdown of the -subj Fields:

    /C=US - Country Name (2 letter code)
    /ST=State - State or Province Name
    /L=City - Locality Name
    /O=Organization - Organization Name
    /CN=localhost - Common Name (typically your domain or localhost)