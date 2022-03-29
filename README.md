# apache-server_installations-commands

#!/bin/sh


## Software  List
## Ubuntu 20.04.2
## Apache/2.4.41
## mysql Ver 8.0.25
## Php 7.4.3
## phpmyadmin
## Composer version 2.1.2
## Curl 7.68.0 
## PHP Module,bcmath,bz2,calendar,Core,ctype,curl,date,dom,exif,FFI,fileinfo,filter,ftp,gd,gettext,gmp,hash,iconv,intl,json,
## libxml,mbstring,mysqli,mysqlnd,openssl,pcntl,pcre,PDO,pdo_mysql,Phar,posix,readline,Reflection,session,shmop,SimpleXML,sockets
## sodium,SPL,standard,sysvmsg,sysvsem,sysvshm,tokenizer,xml,xmlreader,xmlrpc,xmlwriter,xsl,Zend OPcache,zip,zlib,[Zend Modules]
## Zend OPcache
## SSH
## GIT

################################ <<<<===========>>>> Install php7.4 with module 	<<<<===========>>>> ################################

sudo apt-get update

sudo apt-get upgrade -y

sudo apt-get install apache2 -y && sudo a2enmod rewrite && sudo apt-get -y install php php-cgi libapache2-mod-php php-common php-pear php-mbstring && sudo apt-get install -y mysql-server && sudo apt install -y php7.4 libapache2-mod-php7.4 php7.4-common php7.4-gmp php7.4-curl php7.4-intl php7.4-mbstring php7.4-xmlrpc php7.4-mysql php7.4-gd php7.4-bcmath php7.4-xml php7.4-cli php7.4-zip && sudo apt-get install -y php7.4-{cli,bcmath,bz2,intl,gd,mbstring,mysql,zip,opcache,intl,bcmath,xsl,zip,bz2}

############################### <<<<===========>>>> mysql user and passwowd 		<<<<===========>>>> ################################

# mysql

# UPDATE mysql.user SET authentication_string=null WHERE User='root';
# flush privileges;
# ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '12345';
# flush privileges;


############################### <<<<===========>>>> PHPMYADMIN 		<<<<===========>>>> ################################

echo "Include /etc/phpmyadmin/apache.conf" | sudo tee -a sudo nano /etc/apache2/apache2.conf
# sudo apt-get install -y phpmyadmin

################################ <<<<===========>>>> Composer installing prosess 	<<<<===========>>>> ################################# PHPMYADMIN

sudo apt-get update && sudo apt-get install curl 

sudo curl -s https://getcomposer.org/installer | php 

sudo mv composer.phar /usr/local/bin/composer

############################### <<<<===========>>>> permission web folder from user <<<<===========>>>> ################################

sudo rm -rf /var/www/html/*

sudo chown -R $USER:www-data /var/www/html/
sudo chown -R $USER:www-data /var/www/html/*

############################### <<<<===========>>>> permission web folder from user <<<<===========>>>> ################################

##Softeware

sudo apt-get install -y git
