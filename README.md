# html-css

Load Balancing example page:

#user data
```
#!/bin/bash
yum update -y
amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
yum install -y httpd mariadb-server
systemctl start httpd
systemctl enable httpd
usermod -a -G apache ec2-user
chown -R ec2-user:apache /var/www
chmod 2775 /var/www
find /var/www -type d -exec chmod 2775 {} \;
find /var/www -type f -exec chmod 0664 {} \;
wget https://raw.githubusercontent.com/erikanagamine/html-css/main/lb_sample_page.html;
mv lb_sample_page.html /var/www/html/index.html;
echo "Server: <b>"`hostname `"</b>" >> /var/www/html/index.html;
echo " - ">> /var/www/html/index.html;
echo "Page creation date: <b>" `date `"</b>" >> /var/www/html/index.html;
echo " - ">> /var/www/html/index.html;

```
