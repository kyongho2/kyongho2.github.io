---
title: Java Environment Setup
---


# ☕ Java Environment Setup

This guide explains how to set up **Java 17 using Amazon Corretto** and configure **Maven** on your system.

---

## 🔧 Install Amazon Corretto 17

### Import GPG Key and Repository

```bash
sudo rpm --import https://yum.corretto.aws/corretto.key
sudo curl -Lo /etc/yum.repos.d/corretto.repo https://yum.corretto.aws/corretto.repo
```

### Install Java

```bash
sudo dnf install -y java-17-amazon-corretto-devel
```

### Configure Java Version (optional)

```bash
alternatives --config java
```

Sample output:
```
There is 1 program that provides 'java'.

  Selection    Command
-----------------------------------------------
*+ 1           /usr/lib/jvm/java-17-amazon-corretto/bin/java

Enter to keep the current selection[+], or type selection number:
```

---

## 🛠 Set JAVA_HOME

```bash
sudo vi /etc/profile.d/java.sh
```

Add the following:
```bash
JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto
```

Apply the change:
```bash
source /etc/profile.d/java.sh
echo $JAVA_HOME
```

Expected output:
```
/usr/lib/jvm/java-17-amazon-corretto
```

---

## 🧱 Install and Configure Maven

### Install Maven

```bash
sudo dnf install -y maven
```

### Set JAVA_HOME for Maven

```bash
sudo vi ~/.mavenrc
```

Add:
```bash
JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto
```

### Verify Maven

```bash
mvn -v
```

Sample output:
```
Apache Maven 3.6.3 (Red Hat 3.6.3-14)
Maven home: /usr/share/maven
Java version: 11.0.19, vendor: Amazon.com Inc., runtime: /usr/lib/jvm/java-17-amazon-corretto
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "5.14.0-162.23.1.el9_1.x86_64", arch: "amd64", family: "unix"
```
