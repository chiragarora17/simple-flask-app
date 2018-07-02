 ## 1. Install all required dependencies


 sudo yum -y groupinstall "Development Tools"
 sudo yum install -y python python-setuptools python-devel python-pip 
 sudo yum install -y MySQL-python
 sudo yum install -y wget

## 2. Install and Configure Database
sudo wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm
sudo rpm -ivh mysql-community-release-el7-5.noarch.rpm
sudo yum update -y

sudo yum install -y mysql-server mysql

## 3. Start Database Service
  - Start the database service
  sudo systemctl start mysqld

  - Create database and database users
   sudo mysql
   mysql> FLUSH PRIVILEGES;
   mysql> SET PASSWORD FOR 'root'@'localhost' = PASSWORD('password');
   mysql> CREATE DATABASE employee_db;
   mysql> GRANT ALL ON *.* to db_user@'%' IDENTIFIED BY 'password';
   mysql> USE employee_db;
   mysql> CREATE TABLE employees (name VARCHAR(20));

  - Insert some test data
   mysql> INSERT INTO employees VALUES ('JOHN');

## 4. Install and Configure Web Server
Install Python Flash dependency

sudo pip install flask
sudo pip install flask-mysql



