# PostgreSQL 17 Installation Guide (Rocky Linux)

## 1) Add Repository & Disable Default Module
```bash
# Rocky Linux 10
sudo dnf -y install https://download.postgresql.org/pub/repos/yum/reporpms/EL-10-x86_64/pgdg-redhat-repo-latest.noarch.rpm

# (For Rocky 9)
# sudo dnf -y install https://download.postgresql.org/pub/repos/yum/reporpms/EL-9-x86_64/pgdg-redhat-repo-latest.noarch.rpm

# Disable the default AppStream module
sudo dnf -qy module disable postgresql
```

## 2) Install PostgreSQL 17
```bash
sudo dnf -y install postgresql17-server postgresql17
psql --version || /usr/pgsql-17/bin/psql --version
```

## 3) Initialize Database Cluster & Start Service
```bash
sudo /usr/pgsql-17/bin/postgresql-17-setup initdb
sudo systemctl enable --now postgresql-17
systemctl status postgresql-17 --no-pager
```

## 4) Basic Security Setup
```bash
sudo -u postgres psql -c "ALTER USER postgres WITH PASSWORD 'Strong_Password';"

# Example of creating new user/database
sudo -u postgres createuser appuser -P
sudo -u postgres createdb -O appuser appdb
```

## 5) Verify Local Connection
```bash
sudo -u postgres psql -c "\l"
psql -U appuser -d appdb -h 127.0.0.1 -W
```

## 6) Enable Remote Access (Optional)
```bash
# postgresql.conf
listen_addresses = '*'
# pg_hba.conf example
host    all    all    192.168.0.0/24    scram-sha-256

# Open firewall
sudo firewall-cmd --add-service=postgresql --permanent
sudo firewall-cmd --reload

# Reload config
sudo systemctl reload postgresql-17
```

## 7) SELinux Handling for Custom Port
```bash
sudo dnf -y install policycoreutils-python-utils
sudo semanage port -a -t postgresql_port_t -p tcp 5433
sudo systemctl restart postgresql-17
```

## 8) Basic Service Management
```bash
sudo systemctl status postgresql-17
sudo systemctl restart postgresql-17
sudo journalctl -u postgresql-17 -e --no-pager
```

## 9) Backup & Restore Basics
```bash
# Backup
PGPASSWORD='password' pg_dump -U appuser -h 127.0.0.1 -d appdb > appdb_$(date +%F).sql

# Restore
createdb -U appuser -h 127.0.0.1 appdb_restore
psql -U appuser -h 127.0.0.1 -d appdb_restore -f appdb_YYYY-MM-DD.sql
```
