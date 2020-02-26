# AWS TEST Home Page Create


> EC2에 다음과 같이 입력 

<pre><code class='LANG'> 

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
	cd ..
	rm -fR homepage
	chown -R apache:root /var/www/html
	fi
</code></pre>