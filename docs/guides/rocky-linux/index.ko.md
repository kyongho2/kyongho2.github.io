---
title: Rocky Linux 9 설치
---

# 🐧 Rocky Linux 9 기본 설정 튜토리얼

이 문서는 **Rocky Linux 9 설치**부터 **시스템 업데이트**, **한글 입력기 설정**, **Logitech 리시버 설정**까지 데스크탑 사용자가 기본적으로 설정해야 할 내용을 안내합니다.

---

## 💿 Rocky Linux 9 설치

1. **공식 웹사이트에서 ISO 이미지 다운로드**
   → [https://rockylinux.org](https://rockylinux.org)
   데스크탑 용도라면 **DVD ISO** 또는 **GNOME Desktop ISO**를 권장합니다.

2. **부팅 USB 생성**
   - Windows: [Rufus](https://rufus.ie/) 사용
   - Linux/macOS: `dd` 명령어나 `balenaEtcher` 사용

3. **설치 진행**
   - USB로 부팅 후 **“Install Rocky Linux 9”** 선택
   - 언어, 키보드, 시간대, 디스크 파티션 등을 설정
   - 사용자 계정과 루트 암호 설정
   - 설치 완료 후 재부팅

> ⚠ 설치 중 **“소프트웨어 선택”** 단계에서 **"Workstation"** 또는 **"GNOME Desktop"**을 선택하면 GUI 환경이 설치됩니다.

---

## ✅ 시스템 업데이트

최신 보안 패치와 시스템 패키지를 적용합니다:

```bash
sudo dnf update -y
```

---

## 🇰🇷 한글 입력기 설정

### ibus-hangul 설치

```bash
sudo dnf install -y ibus-hangul
```

### 입력기 설정

1. **Settings > Keyboard > Input Sources**로 이동
2. **“+” 버튼** 클릭 후 `Korean` 검색
3. `Korean (Hangul)` 선택 후 추가
4. 항목 옆 **톱니바퀴 아이콘** 클릭
5. **Hangul Toggle Key** 항목에서 `ISO_Level3_Shift` 선택

> 💡 일반적으로 오른쪽 Alt 키(Right Alt/AltGr)가 이 키로 설정됩니다.

---

## 🔌 Logitech 무선 리시버 설정

### EPEL 저장소 추가

```bash
sudo dnf install -y epel-release
```

### Solaar 설치

```bash
sudo dnf install -y solaar
```

설치 후, **Solaar**를 실행하면 Logitech 무선 장치의 상태를 확인하고 설정할 수 있습니다.

---

## 🎉 마무리

Rocky Linux 9 설치와 기본 설정이 완료되었습니다.
필요한 패키지 추가나 개인화 설정 등 다음 단계가 필요하면 언제든지 도와드릴게요.
