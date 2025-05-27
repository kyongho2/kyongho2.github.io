# PostgreSQL 완전 삭제 (Rocky Linux)

이 문서는 Rocky Linux에서 PostgreSQL을 **완전히 제거**하는 절차를 안내합니다. 이 과정은 PostgreSQL 패키지, 데이터, 사용자 계정 등을 모두 삭제합니다.

---

## 1. PostgreSQL 서비스 중지

```bash
sudo systemctl stop postgresql
```

---

## 2. PostgreSQL 패키지 제거

```bash
sudo dnf remove postgresql\*
```

> `postgresql*` 와일드카드는 모든 PostgreSQL 관련 패키지를 제거합니다.

---

## 3. PostgreSQL 사용자 및 그룹 삭제 (선택 사항)

```bash
sudo userdel -r postgres
```

> `-r` 옵션은 `postgres` 사용자의 홈 디렉토리도 함께 삭제합니다.

---

## 4. 데이터 디렉토리 삭제

PostgreSQL의 데이터 디렉토리는 보통 아래 경로 중 하나입니다:

- `/var/lib/pgsql/`
- `/var/lib/pgsql/data/`

디렉토리를 수동으로 삭제하려면:

```bash
sudo rm -rf /var/lib/pgsql
```

> 데이터와 설정이 모두 삭제되므로, 필요 시 백업을 먼저 진행하세요.

---

## 5. 설정 파일 및 로그 삭제 (선택 사항)

```bash
sudo rm -rf /etc/postgresql*
sudo rm -rf /var/log/postgresql*
```

---

## 참고

- 이 과정을 완료하면 PostgreSQL이 시스템에서 완전히 제거됩니다.
- 재설치를 원할 경우 `dnf install postgresql-server` 등을 사용하여 다시 설치할 수 있습니다.
