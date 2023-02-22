## CLIENT-SERVER ARCHITECTURE WITH MYSQL


## Create and configure two-linux based virtual servers on AWS Instance
 ### - i.e MySQL-server and MySQL-client on the EC2 instances


## 1. Install MySQL server software on the MySQL-server Linux server

`sudo apt install mysql-server -y`

### enable the mysql service

`sudo systemctl enable mysql`

![mysql](/images/mysqlserver-enable.PNG)

## 2. Install MySQL client software on MySQL-client Linux server

`sudo apt install mysql-client -y`

## Get the IP address of client

`ip addr show`

![ipaddr](/images/ip-adddr.PNG)


### On the MySQL-server Linux server,run the security script.

`sudo mysql_secure_installation`

### Next, Edit the inbound rule of the security group of the MySQL-server linux server to makes use of the TCP port 3306.

### Also, Allow only the connection of the IP address of the mysql-client to the mysql server linux server instance

## 3. Create user, database and grant privileges.

![db](/images/create-user-db-privileges.PNG)

## 4. Configure MYSQL server to allow connection from remote hosts by replacing '127.0.0.1' to '0.0.0.0'

`sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`

![config](/images/configure-mysql.PNG)

## 5. Connect remotely to mysql server DB engine from mysql-client linux server without using SSH.

![utility](/images/mysql-utility.PNG)

## 6. Confirm successful connection to a remote MySQL-server by performing SQL queries.
`Show databases`

![conn](/images/mysql-conn.PNG)