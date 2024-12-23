
```
**To purge PostgreSQL completely**
sudo systemctl stop postgresql
sudo apt purge postgresql "postgresql-*"
sudo rm -rf /etc/postgresql
sudo rm -rf /var/lib/postgresql
sudo rm -rf /var/log/postgresql
sudo rm -rf /usr/lib/postgresql

find /etc/systemd -name "postgres*"
sudo rm -f <path>

sudo deluser postgres
sudo delgroup postgres

sudo apt autoremove
sudo apt autoclean

**To install the latest version of the PostgreSQL**
apt show postgresql

*If the above command doesn't show the latest version, only then execute the following commands to update your software repository to latest and verify*
*sudo apt install -y postgresql-common
sudo /usr/share/postgresql-common/pgdg/apt.postgresql.org.sh
sudo apt update
apt show postgresql*

sudo apt install postgresql

**To check the PostgreSQL status**
systemctl status postgresql

**To identify the PostgreSQL location**
ps -aux | grep "postgresql"

**To config the PostgreSQL**
cd <config directory path>
*Eg. 
cd /etc/postgresql/16/main/*

sudo cp postgresql.conf postgresql.conf.bak
sudo nano postgresql.conf
sudo systemctl restart postgresql
systemctl status postgresql

**To check whether the PostgreSQL installation process has created the db user**
awk -F ':' '{print $1}' /etc/passwd | grep "postgres"

*If the above command does not show any user, then execute the following command,
sudo adduser postgres*

**Connect with the PostgreSQL server via psql**
su <username>
sudo su postgres
psql

**PSQL basic commands**
\c
\conninfo
\password
\q
exit

**To alter client authentication mechanism**
cd /etc/postgresql/16/main
sudo nano pg_hba.conf
sudo systemctl restart postgresql

psql -h <ipaddress> -p <port> -U <username> -W
```