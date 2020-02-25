TEST Home Page Create

#!/bin/sh
sudo yum -y update
sudo yum -y install httpd git
sudo chkconfig httpd on
sudo systemctl start httpd
# sudo systemctl start httpd.service

if [ ! -f /var/www/html/index.html ]; then
cd /var/www/html
git clone https://github.com/yscoma/homepage.git
cd homepage
mv * ../

chown -R apache:root /var/www/html
fi
