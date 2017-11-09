---
title: Setting Up LAMP Stack on CentOS7
image: https://www.thermo.io/wp-content/themes/thermo/static/images/perks-1.svg
---

# Setting Up LAMP Stack on CentOS7
## One: Getting started
Follow these steps to make sure your system is up to date and to install and properly configure Apache:
1. Make sure your system is up to date:
```
sudo yum update
```
2. Install the latest version of Apache:
```
sudo yum install httpd
```
3. Make sure Apache runs on boot:
```
sudo systemctl enable httpd
```
## Two: Install MySQL (MariaDB)
**Attention:** This guide uses the widely-used MariaDB as a drop-in replacement for MySQL.
1. Install MariaDB:
```
sudo yum install mariadb-server
```
2. Enable MariaDB and initialize on-boot:
```
sudo systemctl enable mariadb
sudo systemctl start mariadb
```
3. As part of best practice, run the MySQL secure installation script to set a root password and other basic security settings:
```
sudo mysql_secure_installation
```
4. When prompted to enter the current root password, press Enter (you have yet to create one).
5. When the next prompt asks to set a root password, select one that follows best security practices, then hit Enter. Hit Enter to accept the default values on all other prompts.
## Three: Install PHP
1. Install PHP with yum:
```
sudo yum install php php-mysql php-pear
```
2. Restart Apache
```
sudo systemctl restart apache
```
The procedure is complete.
