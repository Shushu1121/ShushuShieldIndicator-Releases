# Shushu Shield Indicator

Astral Party의 PvE 플레이 중 렌의 슈슈 쉴드 상태를 더 쉽게 확인할 수 있도록  
화면에 보조 오버레이를 표시하는 Windows용 비공식 보조 도구입니다.

## 다운로드

최신 버전: **v1.24.1**

[Shushu Shield Indicator 최신 버전 다운로드](https://github.com/Shushu1121/ShushuShieldIndicator-Releases/releases/latest)

> v1.24.1: 게임 내 `게임 종료` 버튼 사용 시 Sensor가 Unity/IL2CPP 종료를 막아 응답 없음 상태가 될 수 있던 문제를 수정했습니다.

Windows 10/11, Astral Party Steam Global/INT 클라이언트의 PvE 환경을 기준으로 개발 및 검증되었습니다.

> PvP 모드는 개발/검증 대상이 아니며 동작, 호환성, 안전성을 보장하지 않습니다.

## 사용 안내

![Shushu Shield Indicator 사용 안내](Infographic_KO.png)

## 시연 영상

[![Shushu Shield Indicator v1.24 시연 영상](https://img.youtube.com/vi/gHkvVtvm5-8/maxresdefault.jpg)](https://youtu.be/gHkvVtvm5-8)

이미지를 클릭하면 YouTube 시연 영상으로 이동합니다.

---

## 프로그램 개요

Shushu Shield Indicator는 Astral Party의 PvE 플레이 중 렌의 슈슈 쉴드 상태를 더 쉽게 확인할 수 있도록 화면에 보조 오버레이를 표시하는 비공식 개인용 보조 도구입니다.

제작 목적은 플레이어 개인의 게임 플레이 편의성과 가독성을 높이는 것입니다. 게임사, 서버 또는 다른 플레이어에게 피해를 주거나 게임 결과를 조작하기 위한 목적으로 제작되지 않았습니다.

프로그램은 BepInEx 플러그인인 Sensor가 게임 클라이언트의 로컬 런타임/IL2CPP 상태를 읽고, 그 결과를 `127.0.0.1` 로컬 UDP로 Indicator에 전달하는 구조입니다.

현재 구현에는 다음 기능이 없습니다.

- 게임 서버 패킷 가로채기/변조/위조
- 네트워크 트래픽 조작
- 자동 입력/매크로/자동 플레이
- 게임 수치, 재화, 전투 결과 또는 런타임 상태 변경

단, BepInEx와 Sensor가 게임 프로세스에 로드되는 비공식 모드 방식이므로 게임 개발사/배급사가 공식적으로 승인한 도구라는 의미는 아닙니다.

## 지원/검증 범위

- Windows
- Astral Party Steam Global/INT 클라이언트
- PvE 모드
- 주 모니터 전체화면 권장
- 1920×1080 (16:9) 권장

창모드, 일부 무테두리/특수 창 구성, 비표준 Windows 화면 배율(DPI), 비16:9 해상도, 게임이 주 모니터와 다른 모니터에 표시되는 환경에서는 오버레이 위치가 어긋날 수 있으며 정상 작동을 보장하지 않습니다.

## 최초 실행 및 자동 설치

처음 사용하는 PC에서는 `ShushuShieldIndicator.exe`를 한 번 직접 실행하세요.

프로그램이 Astral Party 설치 경로를 확인하고 필요한 BepInEx와 Sensor를 자동 설치/수리합니다.

게임이 이미 실행 중이고 설치 또는 갱신이 필요한 경우에는 게임 파일을 변경하지 않고 작업을 보류하며, 게임 종료 후 다시 처리합니다.

BepInEx가 처음 설치된 PC에서는 Astral Party 최초 실행 시 IL2CPP interop 파일 생성 때문에 평소보다 게임 시작이 늦을 수 있습니다. 이는 예상 가능한 초기화 과정이며 이후 실행은 보통 더 빨라집니다.

## 자동 실행 및 종료

기본 설정:

- `파티에 렌이 있을 때만 실행`: ON
- `게임에 맞춰 자동 실행 및 종료`: OFF

두 옵션은 동시에 켤 수 없으며 둘 다 끄는 것도 가능합니다.

### 파티에 렌이 있을 때만 실행

- PvE 보드에서 슈슈 쉴드가 감지되면 해당 판에서 Indicator가 자동으로 실행됩니다.
- 판 도중 슈슈 쉴드가 소모되어도 결과 화면까지 Indicator가 유지됩니다.
- 해당 판이 끝나면 Indicator가 정상 종료됩니다.
- 슈슈 쉴드가 감지되지 않는 판에서는 Indicator를 자동으로 실행하지 않습니다.

### 게임에 맞춰 자동 실행 및 종료

- Astral Party 실행에 맞춰 등록된 Indicator를 실행합니다.
- 게임 종료에 맞춰 Indicator도 종료합니다.
- 마지막으로 직접 실행한 Indicator EXE 경로가 자동 실행 대상으로 등록됩니다.

최초 설치 또는 EXE 위치 변경 후에는 Sensor 설치/경로 등록을 위해 새 위치의 Indicator를 한 번 직접 실행하는 것이 좋습니다.

## 오버레이 기능

- **파티원 목록 오버레이**  
  일반 보드의 파티원별 슈슈 쉴드 상태 표시

- **약식 오버레이**  
  유물/칩 선택, 카드 상점, 카드 버리기, 몬스터 선택 계열 화면에서 간략 상태 표시

- **배틀 오버레이**  
  전투 참여자의 슈슈 쉴드 상태 표시

- **수비 행동 가이드**  
  본인이 슈슈 쉴드를 보유한 수비자인 경우 준비/회피 버튼을 파란 링으로 강조

수비 행동 가이드의 반짝이는 파티클 효과는 설정에서 별도로 끌 수 있습니다. 강조 링 자체와 일반 슈슈 쉴드 파티클에는 영향을 주지 않습니다.

스타 코인 송금 창, PAUSE 메뉴, 도감, 설정, 모듈 확인, 맵 설명, 맵 시작 대화 스크립트 화면에서는 Indicator 오버레이가 자동으로 숨겨지고 원래 게임 화면으로 돌아오면 다시 표시됩니다.

수비 행동 가이드는 시각적 안내 기능이며 자동 입력 기능이 아닙니다.

## 조작

- 트레이 아이콘 우클릭: 설정 / 종료
- `F1`: 오버레이 ON/OFF
- `F2`: 프로그램 종료

## 성능 모드

기본 성능 모드는 **일반 사양**입니다.

- **일반 사양**: 더 부드러운 오버레이 애니메이션을 우선
- **저사양**: 판정 정확도는 유지하면서 오버레이 갱신/애니메이션 빈도를 낮춰 시스템 자원 사용 감소

성능이 부담스러운 환경에서는 저사양 모드와 수비 시 버튼 주변 파티클 효과 OFF를 함께 사용할 수 있습니다.

## 인디케이터 사용 GPU

설정 창에서 Shushu Shield Indicator가 사용할 Windows 앱별 그래픽 기본 설정을 선택할 수 있습니다.

- Windows 기본 설정
- 절전 GPU
- **고성능 GPU (권장)**

내장 GPU와 외장 GPU가 함께 있는 일부 PC에서는 `고성능 GPU (권장)` 설정이 투명 오버레이 표시 중 발생할 수 있는 간헐적인 끊김 현상을 줄이는 데 도움이 될 수 있습니다.

이 설정은 Astral Party가 아니라 현재 `ShushuShieldIndicator.exe` 경로에 적용됩니다.

EXE 위치를 변경한 경우 새 위치에서 GPU 설정을 다시 지정해야 할 수 있으며, GPU 설정 변경 후에는 Indicator를 완전히 종료한 뒤 다시 실행하세요.

## 게임 설치 경로

프로그램은 Steam 설치 경로와 `libraryfolders.vdf`를 이용해 여러 Steam 라이브러리를 탐색합니다.

자동 탐지에 실패하면 설정에서 `astralparty_int.exe`가 들어 있는 다음 폴더를 직접 지정하세요.

```text
Astral Party\8vJXnINT
```

## 기존 BepInEx / 모드 사용자

이미 BepInEx가 설치되어 있는 경우 기존 호환 가능한 BepInEx core는 보존하도록 설계되어 있습니다.

Shushu Shield Indicator의 Sensor는 다음 경로에 설치됩니다.

```text
BepInEx\plugins\ShushuShieldIndicator
```

단, 모든 타사 모드 조합과의 호환성을 보장하지는 않습니다.

## 제거

게임과 프로그램을 모두 종료한 뒤 배포 폴더의

```text
ShushuShieldIndicator_Uninstall.exe
```

를 실행하면 게임에 설치된 Shushu Sensor와 로컬 설정을 제거할 수 있습니다.

BepInEx가 이 프로그램에 의해 깨끗한 상태에서 새로 설치되었고 다른 BepInEx 모드가 감지되지 않는 경우에는 BepInEx도 함께 정리합니다.

기존 BepInEx가 있었거나 다른 모드가 감지되는 경우에는 다른 모드를 손상시키지 않도록 BepInEx 자체를 보존하고 Shushu 관련 구성요소만 제거합니다.

## 개인정보 / 통신

현재 버전은 별도 사용자 계정 정보, 비밀번호 또는 개인 데이터를 수집하는 기능이 없습니다.

Sensor와 Indicator 간 상태 전달은 `127.0.0.1` 로컬 UDP를 사용합니다.

프로그램은 게임 경로 탐지를 위해 로컬 Steam 설정/라이브러리 정보를 읽을 수 있습니다.

설정과 자동 실행에 필요한 Indicator EXE 경로는 다음 위치에 저장될 수 있습니다.

```text
%LOCALAPPDATA%\ShushuShieldTracker\config.json
```

## 비공식 도구 및 이용 책임

이 프로그램은 Astral Party 개발사/배급사의 공식 제품이나 공식 지원 도구가 아닙니다.

게임 업데이트, 운영정책 변경 또는 클라이언트 구조 변경으로 인해 언제든지 작동하지 않거나 예상치 못한 문제가 생길 수 있습니다.

프로그램 제작자는 악의적인 목적이나 다른 이용자의 플레이를 방해하기 위한 목적으로 이 도구를 제공하지 않습니다. 그러나 이러한 제작 의도는 게임 운영정책상 사용 허가를 의미하지 않습니다.

사용자는 본인이 이용하는 게임의 이용약관/운영정책을 직접 확인하고 본인의 판단과 책임 하에 사용해야 합니다. 관련 법령상 허용되는 범위에서 원제작자는 프로그램 사용으로 인한 게임 실행 문제, 데이터 또는 설정 손실, 계정 이용 제한 또는 제재, 다른 프로그램이나 모드와의 충돌 등 직접·간접적인 손해를 보증하거나 책임지지 않습니다.

## 이용 및 배포 조건

Shushu Shield Indicator는 오픈소스 소프트웨어로 제공되는 프로그램이 아닙니다.  
아래에서 명시적으로 허용한 범위를 제외한 권리는 원제작자에게 유보됩니다.

공식 배포처: [ShushuShieldIndicator-Releases](https://github.com/Shushu1121/ShushuShieldIndicator-Releases)

본 문서에서 **원본 배포물**은 원제작자가 공식 GitHub 저장소 및 GitHub Releases를 통해 직접 배포한 `ShushuShieldIndicator_v1.24.1_Windows.zip`을 내용 변경 없이 그대로 보존한 배포물을 의미합니다.

- 원제작자와 공식 배포처 등 원본 출처를 명시하는 경우 원본 배포물의 비상업적 공유 및 재배포를 허용합니다.
- 프로그램 파일, 문서, 라이선스 고지 등 원본 구성요소를 임의로 수정하거나 제거하지 않은 상태로 배포해야 합니다.
- 상업적 이용은 허용하지 않습니다.
- 본 프로그램을 자신 또는 제3자가 제작한 것처럼 표시하거나 원제작자 정보를 삭제·변경하여 제작자를 오인하게 하는 행위를 금지합니다.
- 수정본, 재포장본 또는 파생물의 공개 재배포에는 원제작자의 사전 허가가 필요합니다.
- 저작권 고지 및 이용 조건을 삭제하거나 변경해서는 안 됩니다.
- 이용 조건을 위반한 경우 공유 및 재배포 허가는 종료되며, 위반 상태의 배포물을 계속 공개하거나 재배포할 수 없습니다.

자세한 내용은 [LICENSE.txt](LICENSE.txt)를 확인하세요.

Astral Party의 게임 그래픽, 이펙트, 이미지, 캐릭터, 로고, 명칭 및 기타 게임 자산에 대한 권리는 해당 권리자에게 있습니다.

본 배포물에 그러한 게임 자산의 일부가 포함되어 있더라도, Shushu Shield Indicator의 이용 및 배포 조건은 해당 게임 자산에 대한 별도의 이용권, 소유권 또는 재배포 권리를 부여하는 것으로 해석되지 않습니다.

제3자 라이브러리 및 도구의 별도 라이선스와 고지는 `THIRD_PARTY_NOTICES.txt` 및 `LICENSES` 폴더를 따릅니다.

## 배포 파일

공식 배포 ZIP:

```text
ShushuShieldIndicator_v1.24.1_Windows.zip
└─ dist\
   ├─ ShushuShieldIndicator.exe
   ├─ ShushuShieldIndicator_Uninstall.exe
   ├─ Infographic_KO.png
   ├─ README_KO.txt
   ├─ RELEASE_NOTES.txt
   ├─ LICENSE.txt
   ├─ THIRD_PARTY_NOTICES.txt
   ├─ ShushuShieldIndicator.build.json
   ├─ SHA256SUMS.txt
   └─ LICENSES\
```

`LICENSE.txt`는 Shushu Shield Indicator 자체의 이용 및 배포 조건입니다.

`THIRD_PARTY_NOTICES.txt`와 `LICENSES` 폴더는 배포물에 포함된 제3자 라이브러리 및 도구의 라이선스/고지용입니다.

`SHA256SUMS.txt`를 이용하면 배포 파일의 SHA-256을 확인할 수 있습니다.

이 프로그램은 코드 서명이 없는 PyInstaller EXE이므로 Windows SmartScreen 또는 일부 백신 제품에서 경고가 표시될 수 있습니다.

## Credits

**렌이좋은데슈슈쉴드자꾸날려먹어서답답했던아붕이**
