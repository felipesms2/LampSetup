# LampSetup
For Docker and Virtual Machines even local runtime enviroment that need php backend

  sudo su <br>
  apt update <br>
  apt upgrade -y <br>
  apt install sqlite3 apache2 php phpunit php-sqlite3 php-interbase php-odbc php-mysql php-mssql php-curl mariadb-server openssh-server composer git nodejs npm nano neovim vim lynx -y   
  
service mysql enable && service mysql start && service apache2 start
  
CREATE USER 'superuser'@'%' IDENTIFIED BY 'S3nh4c0mPalavr45qualq3r';

GRANT ALL PRIVILEGES ON *.* TO 'S3nh4c0mPalavr45qualq3r'@'%' WITH GRANT OPTION;
FLUSH PRIVILEGES;
EXIT;
