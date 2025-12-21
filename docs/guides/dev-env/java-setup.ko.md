---
title: Java 환경 설치
---

# ☕ Java 환경 설치

이 문서는 **Amazon Corretto 17 기반 Java 환경 설정**과 **Maven 설치 및 구성** 방법을 안내합니다.

---

## 🔧 Amazon Corretto 17 설치

### Java 설치

**다운로드**

Amazon Corretto 17 RPM 패키지를 공식 GitHub 릴리즈 페이지에서 다운로드합니다:

```bash
https://github.com/corretto/corretto-17/releases
```

> 시스템에 맞는 RPM 파일을 선택하여 다운로드합니다 (예: java-17-amazon-corretto-devel-17.0.17.10-1.x86_64.rpm).

**설치**

다운로드한 RPM 파일을 dnf 명령어로 설치합니다:

```bash
sudo dnf install -y java-17-amazon-corretto-devel-17.0.17.10-1.x86_64.rpm
```

### Java 버전 설정 (옵션)

```bash
alternatives --config java
```

예시 출력:
```
There is 1 program that provides 'java'.

  Selection    Command
-----------------------------------------------
*+ 1           /usr/lib/jvm/java-17-amazon-corretto/bin/java

Enter to keep the current selection[+], or type selection number:
```

---

## 🛠 JAVA_HOME 설정

```bash
sudo vi /etc/profile.d/java.sh
```

내용 추가:
```bash
JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto
```

반영:
```bash
source /etc/profile.d/java.sh
echo $JAVA_HOME
```

출력 예시:
```
/usr/lib/jvm/java-17-amazon-corretto
```

---

## 🛠 Maven 설치 및 설정

### Maven 설치

```bash
sudo dnf install -y maven
```

### JAVA_HOME 지정

```bash
sudo vi ~/.mavenrc
```

내용 추가:
```bash
JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto
```

### Maven 버전 확인

```bash
mvn -v
```

예시 출력:
```
Apache Maven 3.6.3 (Red Hat 3.6.3-14)
Maven home: /usr/share/maven
Java version: 11.0.19, vendor: Amazon.com Inc., runtime: /usr/lib/jvm/java-17-amazon-corretto
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "5.14.0-162.23.1.el9_1.x86_64", arch: "amd64", family: "unix"
```
