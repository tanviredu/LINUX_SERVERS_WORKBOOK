sudo zypper install apache2
sudo systemctl start apache2
sudo systemctl enable apache2
sudo zypper install mariadb
'/usr/bin/mysqladmin' -u root password 'your password'
sudo systemctl start mysql
sudo systemctl enable mysql

//find repo for php if there is not in your os
sudo zypper addrepo http://download.opensuse.org/repositories/devel:/languages:/php:/php56/SLE_12_SP3/devel:languages:php:php56.repo
sudo zypper update
sudo zypper install php5 php5-mysql apache2-mod_php5
sudo a2enmod php5
sudo systemctl restart apache2 // sudo service apache2 restart
vim /srv/www/htdocs/info.php
########################
<?php
    phpinfo();
?>
#######################

visit localhost/info.php

sudo zypper install phpMyAdmin    //case sensetive

// this may change your version of php and everything to 7
// dont panic its even better


//give php permission
cd /var/lib
sudo chmod 777 -R php7 // or 5 what you using

//give phpMyAdmin permission


cd /srv/www/htdocs

sudo chmod -R 775 phpMyAdmin    // 775 is very imp you cant do 777




//now install composer for php

//first check is the php in the /user/bin 

=>which php

output will be
/usr/bin/php

//first get the composer

sudo zypper install php-composer


thats it



