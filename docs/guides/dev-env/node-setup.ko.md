---
title: Node.js 환경 설치 가이드
---

# Node.js 환경 설치 가이드

이 가이드는 Node.js를 설치하고 관리하기 위해 Node Version Manager (NVM)을 사용하는 방법을 안내합니다.
NVM을 사용하면 여러 버전의 Node.js를 손쉽게 설치하고 관리할 수 있습니다.

## 1. NVM 설치

먼저, NVM을 설치해야 합니다. 아래 명령어를 실행하여 NVM을 설치합니다:

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
```

이 명령은 nvm 설치 스크립트를 다운로드하고 실행합니다. 설치가 완료되면, 쉘 환경을 다시 로드하여 nvm 명령어를 사용할 수 있도록 설정합니다.

```
source ~/.bashrc
```

## 2. NVM 설치 확인

NVM이 제대로 설치되었는지 확인하려면 아래 명령어를 실행해보세요:

```
command -v nvm
```

설치가 정상적으로 완료되었다면 nvm 명령어의 경로가 출력됩니다.

## 3. LTS 버전 목록 확인

NVM을 사용하여 다양한 Node.js 버전을 설치할 수 있습니다. 현재 사용할 수 있는 LTS (Long-Term Support) 버전 목록을 확인하려면 아래 명령어를 사용합니다:

```
nvm list-remote | grep "Latest LTS"
```

이 명령어는 다음과 같은 결과를 출력할 수 있습니다:

```
v4.9.1   (Latest LTS: Argon)
v6.17.1   (Latest LTS: Boron)
v8.17.0   (Latest LTS: Carbon)
v10.24.1   (Latest LTS: Dubnium)
v12.22.12   (Latest LTS: Erbium)
v14.21.3   (Latest LTS: Fermium)
v16.20.0   (Latest LTS: Gallium)
v18.16.0   (Latest LTS: Hydrogen)
```

위 목록에서 원하는 LTS 버전을 선택하여 설치할 수 있습니다.

## 4. Node.js 버전 설치

원하는 버전을 설치하려면 아래와 같이 명령어를 실행합니다. 예를 들어, Node.js v16.20.2를 설치하려면 다음 명령어를 사용합니다:

```
nvm install v16.20.2
```

이 명령어는 Node.js v16.20.2 버전을 다운로드하여 설치합니다.

## 5. Node.js 버전 확인

설치가 완료되면, 아래 명령어를 실행하여 현재 설치된 Node.js 버전을 확인할 수 있습니다:

```
node -v
```

정상적으로 설치되었다면, 다음과 같은 출력이 표시됩니다:

```
v16.20.2
```

## 6. 여러 버전의 Node.js 관리

NVM을 사용하면 여러 버전의 Node.js를 동시에 설치하고 쉽게 전환할 수 있습니다. 설치된 버전 목록을 확인하려면 다음 명령어를 사용합니다:

```
nvm ls
```

특정 버전으로 전환하려면 다음 명령어를 사용합니다:

```
nvm use v16.20.2
```

이렇게 하면 v16.20.2 버전의 Node.js가 활성화됩니다.

## 7. 기본 Node.js 버전 설정

기본적으로 사용할 Node.js 버전을 설정하려면 아래 명령어를 사용합니다:

```
nvm alias default v16.20.2
```

이 설정은 새로운 터미널 세션을 시작할 때마다 자동으로 v16.20.2 버전을 사용하도록 합니다.

## 결론

이 가이드를 통해 NVM을 사용하여 Node.js를 손쉽게 설치하고 관리하는 방법을 배웠습니다. 여러 버전을 설치하고 전환하는 등의 작업을 할 수 있어 개발 환경을 더욱 효율적으로 구성할 수 있습니다.
