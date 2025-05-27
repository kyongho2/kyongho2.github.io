# Installing pgAdmin on Rocky Linux

This guide provides step-by-step instructions to install **pgAdmin** on a Rocky Linux system.

---

## Prerequisites

- Rocky Linux 8 or 9 installed  
- Root or sudo privileges  
- PostgreSQL installed (optional but recommended for testing)  

---

## Step 1: Update System

```bash
sudo dnf update -y
```

## Step 2: Install EPEL Repository

pgAdmin requires some dependencies available in the EPEL repository.

```bash
sudo dnf install epel-release -y
```

## Step 3: Install Required Dependencies

```bash
sudo dnf install -y \
    python3 \
    python3-pip \
    python3-devel \
    gcc \
    gcc-c++ \
    make \
    libffi-devel \
    openssl-devel \
    redhat-rpm-config \
    wget
```

## Step 4: Add pgAdmin Repository

Add the official pgAdmin repository to your system.

```bash
sudo rpm -i https://ftp.postgresql.org/pub/pgadmin/pgadmin4/yum/pgadmin4-fedora-repo-2-1.noarch.rpm
```

## Step 5: Install pgAdmin4

You can choose between desktop mode and web mode.
For Desktop Mode:

```bash
sudo dnf install pgadmin4-desktop -y
```

For Web Mode:

```bash
sudo dnf install pgadmin4-web -y
```

## Step 6: Configure pgAdmin4 (Web Mode Only)

Run the setup script to configure the web mode:

```bash
sudo /usr/pgadmin4/bin/setup-web.sh
```

You will be prompted to create an email and password for the pgAdmin web interface login.

## Step 7: Start and Enable Apache Web Server (for Web Mode)

pgAdmin web mode uses Apache HTTP Server.

```bash
sudo systemctl enable httpd
sudo systemctl start httpd
```

## Step 8: Access pgAdmin

- Desktop Mode: Launch pgAdmin from your applications menu.
- Web Mode: Open a browser and navigate to:
  `http://<your_server_ip>/pgadmin4`

## Step 9: (Optional) Firewall Configuration for Web Mode

Allow HTTP traffic if firewall is enabled:

```bash
sudo firewall-cmd --add-service=http --permanent
sudo firewall-cmd --reload
```

## Troubleshooting

- If pgAdmin fails to start, check logs at:
  `/var/log/httpd/error_log`
- Make sure all required dependencies are installed.

## References

- pgAdmin Official Documentation
- PostgreSQL RPM Repository

