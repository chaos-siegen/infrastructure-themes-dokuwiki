# taken from https://www.dokuwiki.org/install:ubuntu

sudo apt-get update && sudo apt-get upgrade
sudo apt-get install apache2 libapache2-mod-php php-xml
sudo a2enmod rewrite
cd /var/www
sudo wget https://download.dokuwiki.org/src/dokuwiki/dokuwiki-stable.tgz
sudo tar xvf dokuwiki-stable.tgz
sudo mv dokuwiki-*/ dokuwiki
sudo chown -R www-data:www-data /var/www/dokuwiki
sudo nano /etc/apache2/sites-enabled/000*.conf
cd /etc/apache2/sites-available
sudo touch apache2-dokuwiki.conf
sudo tee apache2-dokuwiki.conf <<'EOF'
<VirtualHost 127.0.0.1>
        DocumentRoot /var/www/dokuwiki
 	ServerName localhost
</VirtualHost>
EOF
sudo a2ensite apache2-dokuwiki
sudo service apache2 reload
sed se /etc/apache2/apache2.conf
#  Change AllowOverrides setting in Apache2 to use .htaccess files for security.
#
#sudo nano /etc/apache2/apache2.conf
#
#    For directory /var/www/ replace
#    AllowOverride None
#    with
#    AllowOverride All
sudo service apache2 restart



# Done
# Go to 127.0.0.1/install.php
# config

#########################################
#########################################

cd to this repo

Now get minimal template to start with

git clone git@github.com:selfthinker/dokuwiki_template_starter.git
git checkout minimal

#########################################
#########################################
#########################################

Now Read

https://www.dokuwiki.org/template:starter
http://blog.andreas-haerter.com/2011/03/16/how-to-create-a-maintainable-dokuwiki-template
https://www.dokuwiki.org/devel%3Acss#templates_styles


