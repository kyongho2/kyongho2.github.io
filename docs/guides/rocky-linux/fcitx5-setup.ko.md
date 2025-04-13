---
title: Fcitx5 입력기 설치
---

# Fcitx5 입력기 설치

## 1. Fcitx5 및 언어 모듈 설치

```bash
sudo dnf install fcitx5 fcitx5-configtool \
fcitx5-gtk2 fcitx5-gtk3 fcitx5-gtk4 fcitx5-qt \
fcitx5-hangul fcitx5-mozc
```

## 2. 환경 변수 설정

### ~/.xprofile 또는 ~/.bashrc 파일에 다음 내용 추가:

```bash
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```

### 적용:

```bash
source ~/.xprofile
# 또는
source ~/.bashrc
```

## 3. 자동 실행 설정

```bash
mkdir -p ~/.config/autostart
cp /usr/share/applications/org.fcitx.Fcitx5.desktop ~/.config/autostart/
```

## 4. Fcitx5 구성 도구 실행

```bash
fcitx5-configtool
```

## 5. 재시작 또는 로그아웃

변경 사항을 반영하려면 시스템을 재시작하거나 로그아웃하세요.

## 6. 입력기 상태 확인

```bash
echo $GTK_IM_MODULE
echo $QT_IM_MODULE
echo $XMODIFIERS
fcitx5-diagnose
```
