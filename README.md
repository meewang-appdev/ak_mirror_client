# AkMirrorEdge

![Flutter](https://img.shields.io/badge/Flutter-3.0%2B-02569B?logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-3.11.4-0175C2?logo=dart&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-Core-000000?logo=rust&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20Android%20%7C%20iOS%20%7C%20Web-2ea44f)
![License](https://img.shields.io/badge/License-AGPL--3.0-red.svg)

`AkMirrorEdge`는 RustDesk의 Flutter 클라이언트 `flutter_hbb`를 기반으로 운영 목적에 맞게 커스터마이징한 원격 제어 애플리케이션입니다. Flutter UI, Rust 네이티브 코어, `flutter_rust_bridge` 기반 FFI 계층을 결합해 원격 데스크톱 제어, 파일 전송, 포트 포워딩, 채팅, 터미널, 카메라 뷰 기능을 제공합니다.

> [!IMPORTANT]
> 이 저장소는 일반적인 Flutter 앱처럼 의존성을 자유롭게 업데이트하는 구조가 아닙니다. 현재 조합은 Rust 브리지, 네이티브 라이브러리, 플랫폼 셸이 함께 검증된 운영 기준점입니다.

> [!WARNING]
> `pubspec.yaml` 및 `pubspec.lock`의 라이브러리 버전은 고정 운영 값입니다. 임의 업그레이드, 다운그레이드, 교체를 절대 금지합니다. 특히 `flutter_rust_bridge`, RustDesk 계열 git 의존성, 렌더링/플랫폼 연동 라이브러리를 바꾸면 ABI 불일치, 브리지 재생성 문제, 런타임 크래시가 발생할 수 있습니다.

> [!CAUTION]
> Android/iOS의 Rust 네이티브 라이브러리는 변경 불가입니다. 아래 기존 검증본을 반드시 사용해야 하며, 임의 교체 또는 재빌드 산출물 반영은 금지합니다.
> - Android: `android/app/src/main/jniLibs/arm64-v8a/librustdesk.so`
> - iOS: `ios/Libraries/liblibrustdesk.a`

> [!NOTE]
> 아래 `고정 라이브러리 버전` 섹션은 현재 [`pubspec.yaml`](pubspec.yaml) 기준 운영 스냅샷입니다. README에 적힌 버전과 실제 파일 버전은 항상 동일하게 유지해야 합니다.

## 개요

| 항목 | 값 |
| --- | --- |
| 프로젝트명 | `AkMirrorEdge` |
| 패키지명 | `flutter_hbb` |
| 앱 버전 | `1.4.4+64` |
| Flutter/Dart 환경 | Flutter SDK `3.41.6`, Dart SDK `^3.11.4` |
| Rust 브리지 | `flutter_rust_bridge` `1.80.1` |
| 핵심 진입점 | [`lib/main.dart`](lib/main.dart) |
| 핵심 세션 컨트롤러 | [`lib/models/model.dart`](lib/models/model.dart) |
| 생성 브리지 | [`lib/generated_bridge.dart`](lib/generated_bridge.dart) |
| 지원 플랫폼 | Windows, macOS, Linux, Android, iOS, Web |

