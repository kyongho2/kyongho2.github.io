# PostgreSQL 17 Installation Guide (Rocky Linux 9)

---

## 1. Install the repository RPM

```bash
sudo dnf install -y https://download.postgresql.org/pub/repos/yum/reporpms/EL-9-x86_64/pgdg-redhat-repo-latest.noarch.rpm
```

---

## 2. Disable the built-in PostgreSQL module

```bash
sudo dnf -qy module disable postgresql
```

---

## 3. Install PostgreSQL 17

```bash
sudo dnf install -y postgresql17-server
```

---

## 4. Optionally initialize the database and enable automatic start

```bash
sudo /usr/pgsql-17/bin/postgresql-17-setup initdb
sudo systemctl enable postgresql-17
sudo systemctl start postgresql-17
```

---

## Note (Comparison with older commands)

In older PostgreSQL versions, the following commands were used:

```bash
postgresql-setup --initdb
systemctl enable postgresql.service
systemctl start postgresql.service
```

In PostgreSQL 17, make sure to use the `postgresql-17` service name.
