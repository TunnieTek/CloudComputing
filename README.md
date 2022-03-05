#MUSIC
#GROUP 1 - PBIT17101
Here are some instructions on how to upload the system to the AWS server.
#####
- Open Xshell and connect AWS with IP Public
After the connection is successful, type the following commands:
sudo yum update -y 
sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
sudo yum install -y httpd mariadb-server


sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd
sudo systemctl stop httpd



sudo chown -R apache:apache /var/www/html
sudo ls -ld /var/www/html



sudo  find /var/www/html -type d -exec sudo chmod 775 {} \;
sudo  find /var/www/html -type f -exec sudo chmod 664 {} \;


sudo systemctl start mariadb
sudo systemctl enable mariadb
sudo systemctl status mariadb


sudo yum install php-mbstring -y
sudo systemctl restart httpd
sudo systemctl restart php-fpm



sudo yum -y install git
cd /var/www/html
git clone https://github.com/Tunniez/CloudComputing
mv * CloudComputing /var/www/html

cd /var/www/html
ls -l (ls -l to check list)

cd wp
cp wp-config-sample.php wp-config.php
vi wp-config.php

cd /etc/httpd/conf.d
vi group1-pbit17101.vn.conf
