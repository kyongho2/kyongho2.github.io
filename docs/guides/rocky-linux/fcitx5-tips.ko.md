---
title: Fcitx5 추가 팁
---

# 💡 Fcitx5 추가 팁

## Chromium/Chrome 호환 문제 해결

Fcitx5는 Chrome 또는 Chromium 기반 브라우저에서 IBus보다 더 안정적으로 작동하는 경우가 많습니다. Chrome에서 입력기 인식이 안될 경우, Fcitx5로 전환하면 해결되는 경우가 많습니다.

## GNOME 환경에서 트레이 아이콘이 보이지 않을 경우

GNOME에서는 기본적으로 트레이 아이콘이 표시되지 않을 수 있습니다. 이 경우 `TopIcons Plus` 같은 확장을 설치하여 입력기 상태 표시 아이콘을 확인할 수 있습니다.

- [GNOME Extensions 사이트](https://extensions.gnome.org/)
- 검색어: `TopIcons Plus`

## 테마 적용

Fcitx5는 다양한 테마를 지원합니다. 예를 들어 `fcitx5-material-color` 테마를 설치하면 현대적이고 깔끔한 입력기 외형을 구성할 수 있습니다.

### 설치 예시:

```bash
git clone https://github.com/hosxy/Fcitx5-Material-Color ~/.local/share/fcitx5/themes/Fcitx5-Material-Color
```

### 적용 방법:

```bash
fcitx5-configtool > Appearance 탭에서 테마 선택
```

## 입력기 전환 단축키 변경

기본 설정 외에 `Shift + Space`, `Hangul` 키 등으로 전환하고 싶다면 Fcitx5 설정 도구에서 단축키 탭을 통해 변경 가능합니다.
