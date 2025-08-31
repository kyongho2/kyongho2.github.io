# PostgreSQL 17 설치 가이드 (Rocky Linux 기준)

## 1) 저장소 추가 & 모듈 비활성화
```bash
# Rocky Linux 10
sudo dnf -y install https://download.postgresql.org/pub/repos/yum/reporpms/EL-10-x86_64/pgdg-redhat-repo-latest.noarch.rpm

# (Rocky 9인 경우)
# sudo dnf -y install https://download.postgresql.org/pub/repos/yum/reporpms/EL-9-x86_64/pgdg-redhat-repo-latest.noarch.rpm

# 기본 AppStream 모듈 비활성화
sudo dnf -qy module disable postgresql
```

## 2) PostgreSQL 17 설치
```bash
sudo dnf -y install postgresql17-server postgresql17
psql --version || /usr/pgsql-17/bin/psql --version
```

## 3) 데이터베이스 클러스터 초기화 & 서비스 시작
```bash
sudo /usr/pgsql-17/bin/postgresql-17-setup initdb
sudo systemctl enable --now postgresql-17
systemctl status postgresql-17 --no-pager
```

## 4) 기본 보안 설정
```bash
sudo -u postgres psql -c "ALTER USER postgres WITH PASSWORD '강한_비밀번호';"

# 새 유저/DB 생성 예시
sudo -u postgres createuser appuser -P
sudo -u postgres createdb -O appuser appdb
```

## 5) 로컬 접속 확인
```bash
sudo -u postgres psql -c "\l"
psql -U appuser -d appdb -h 127.0.0.1 -W
```

## 6) 원격 접속 열기(필요 시)
```bash
# postgresql.conf 수정
listen_addresses = '*'
# pg_hba.conf 수정 예시
host    all    all    192.168.0.0/24    scram-sha-256

# 방화벽 오픈
sudo firewall-cmd --add-service=postgresql --permanent
sudo firewall-cmd --reload

# 설정 반영
sudo systemctl reload postgresql-17
```

## 7) 포트 변경 시 SELinux 처리
```bash
sudo dnf -y install policycoreutils-python-utils
sudo semanage port -a -t postgresql_port_t -p tcp 5433
sudo systemctl restart postgresql-17
```

## 8) 서비스 관리 기본 명령
```bash
sudo systemctl status postgresql-17
sudo systemctl restart postgresql-17
sudo journalctl -u postgresql-17 -e --no-pager
```

## 9) 백업/복구 기본
```bash
# 백업
PGPASSWORD='비번' pg_dump -U appuser -h 127.0.0.1 -d appdb > appdb_$(date +%F).sql

# 복구
createdb -U appuser -h 127.0.0.1 appdb_restore
psql -U appuser -h 127.0.0.1 -d appdb_restore -f appdb_YYYY-MM-DD.sql
```
