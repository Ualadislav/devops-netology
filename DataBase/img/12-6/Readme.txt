sudo -i
apt update
apt install mysql-server mysql-client
mkdir -p /var/log/mysql или проверить наличие /var/log/mysql/
mysqld --initialize
chown -R mysql: /var/log/mysql
chown -R mysql: /var/lib/mysql
nano /etc/mysql/mysql.conf.d/mysqld.cnf
 bind-address            = 0.0.0.0
 mysqlx-bind-address     = 0.0.0.0
 server-id               = 1
 log_bin                 = /var/log/mysql/mysql.log
 
systemctl restart mysql.service
systemctl status mysql.service
