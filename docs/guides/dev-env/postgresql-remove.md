# Completely Removing PostgreSQL (Rocky Linux)

This document outlines the steps to **completely remove** PostgreSQL from Rocky Linux, including all packages, data, and the user account.

---

## 1. Stop the PostgreSQL Service

```bash
sudo systemctl stop postgresql
```

---

## 2. Remove PostgreSQL Packages

```bash
sudo dnf remove postgresql\*
```

> The `postgresql*` wildcard removes all related PostgreSQL packages.

---

## 3. Delete PostgreSQL User and Group (Optional)

```bash
sudo userdel -r postgres
```

> The `-r` option also removes the home directory of the `postgres` user.

---

## 4. Delete Data Directory

PostgreSQL's data directory is usually located at one of the following paths:

- `/var/lib/pgsql/`
- `/var/lib/pgsql/data/`

To remove it manually:

```bash
sudo rm -rf /var/lib/pgsql
```

> Be cautious: this will delete all data and configuration. Back up anything important first.

---

## 5. Delete Configuration and Log Files (Optional)

```bash
sudo rm -rf /etc/postgresql*
sudo rm -rf /var/log/postgresql*
```

---

## Notes

- After completing these steps, PostgreSQL will be completely removed from your system.
- To reinstall, use `dnf install postgresql-server` or similar.
