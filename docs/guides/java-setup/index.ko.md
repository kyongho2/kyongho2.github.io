---
title: Java Environment Setup
---

# Java Environment Setup

```
sudo rpm --import https://yum.corretto.aws/corretto.key
sudo curl -Lo /etc/yum.repos.d/corretto.repo https://yum.corretto.aws/corretto.repo
```

```
sudo dnf install -y java-17-amazon-corretto-devel
```

```
alternatives --config java
```

> There is 1 program that provides 'java'.
>
>   Selection    Command
> -----------------------------------------------
> *+ 1           /usr/lib/jvm/java-17-amazon-corretto/bin/java
>
> Enter to keep the current selection[+], or type selection number:

```
sudo vi /etc/profile.d/java.sh
```

> JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto

```
source /etc/profile.d/java.sh
echo $JAVA_HOME
```

> /usr/lib/jvm/java-17-amazon-corretto

**Maven Settings**

```
sudo dnf install -y maven
```

```
sudo vi ~/.mavenrc
```

> JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto

```
mvn -v
```

> Apache Maven 3.6.3 (Red Hat 3.6.3-14)
> Maven home: /usr/share/maven
> Java version: 11.0.19, vendor: Amazon.com Inc., runtime: /usr/lib/jvm/java-17-amazon-corretto
> Default locale: en_US, platform encoding: UTF-8
> OS name: "linux", version: "5.14.0-162.23.1.el9_1.x86_64", arch: "amd64", family: "unix"
