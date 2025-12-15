# 🚀 bwapi-linux: Linux용 StarCraft AI 템플릿

<p align="center">
데이브 처칠 교수의 STARTcraft 템플릿을 Linux 및 macOS 환경에 맞춰
재구성했습니다. Wine과 MinGW-w64를 사용하여 Unix 기반 시스템에서 BWAPI 봇 개발을
시작하세요.
</p>

## 🌟 Overview

이 저장소는 BWAPI(Brood War API)를 사용하여 StarCraft: BroodWar AI 개발을 가능한
한 빨리 시작할 수 있도록 Linux 친화적으로 간소화된 템플릿을 제공합니다.

이는 인기 있는 davechurchill/STARTcraft 템플릿을 기반으로 Linux 개발자들을 위해
특별히 수정된 버전입니다.

## 🎓 Tutorials

StarCraft AI 프로그래밍이 처음이신가요? 데이브 처칠 교수의 다음 입문용 비디오
튜토리얼을 시청해 보세요.

- Starcraft AI Intro: https://www.youtube.com/watch?v=czhNqUxmLks
- STARTcraft Tutorial: https://www.youtube.com/watch?v=FEEkO6__GKw

## 🛠️ Setup Instructions for Linux

이 가이드는 Linux 환경에서 봇을 컴파일하고 실행하는 데 필요한 의존성 및 파일을
설정하는 과정을 안내합니다.

1. Initialization

저장소를 로컬 머신에 복제합니다.

```bash
git clone https://github.com/TinyProbe/bwapi-linux
cd bwapi-linux
```

2. Install Dependencies

게임 실행을 위한 Wine과, Wine에서 에뮬레이트 되는 Windows 환경용 봇을 크로스
컴파일하기 위한 MinGW-w64가 필요합니다.

```bash
# Wine 설치 (32-bit 아키텍처 추가 및 Wine 설치)
sudo dpkg --add-architecture i386
sudo apt update
sudo apt install wine

# MinGW-w64 설치 (Windows용 크로스 컴파일러)
sudo apt install build-essential mingw-w64
```

3. StarCraft Game Setup

필수 StarCraft: BroodWar 1.16.1 아카이브를 다운로드하여 이 저장소의 루트
디렉터리에 배치해야 합니다.

[Starcraft Broodwar 1.16.1](https://drive.google.com/file/d/1q4gib8OQ0CMDMBorhwWwta135uqwlCSk/view?usp=sharing)

이후, 게임 파일의 압축을 해제합니다.

```bash
# starcraft.tar.xz 파일의 압축 해제
tar -xJf starcraft.tar.xz
```

4. Build the Bot

제공된 Makefile을 사용하여 봇 소스 코드를 컴파일합니다. 이 명령은 MinGW-w64를
사용하여 크로스 컴파일을 수행합니다.

```bash
make
```

5. Run the Bot

제공된 run.sh 스크립트는 필요한 Wine 환경 설정과 함께 StarCraft 및 BWAPI 봇
실행을 간편하게 처리합니다.

```bash
bash run.sh
```

6. Cleanup

생성된 바이너리 파일을 제거하여 깔끔한 상태를 유지하려면 다음 명령어를
사용합니다.

```bash
make clean
```

## 🔗 Related Links

- Base Template: https://github.com/davechurchill/STARTcraft
- BWAPI: https://github.com/bwapi/bwapi
