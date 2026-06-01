# Hello, I'm kyoung-mo 👋
**임베디드 SW 개발자를 목표로 공부하고 있습니다.**  
CAN 통신 · STM32 · Linux · Raspberry Pi를 주로 다루고 있어요.

[![Velog](https://img.shields.io/badge/Velog-20C997?style=for-the-badge&logo=velog&logoColor=white)](https://velog.io/@mommers/posts)

---

## About Me ✨

| 기간 | 활동 / 경력 | 주요 내용 |
|---|---|---|
| 2025.12 ~ 2026.07 | Intel Edge AI SW 아카데미 | 임베디드 소프트웨어 교육 |
| 2020.02 ~ 2026.02 | 강원대학교(춘천) | 전기전자공학과 졸업 |
| 2025.02 ~ 2025.08 | 지능형시스템최적화 연구실 (학부연구생) | CAN 이상탐지, Hailo 엣지 AI 최적화 |
| 2025.11 | IT대학 졸업작품 경진대회 장려상 | RPi5 기반 얼굴 인식 출입 통제 시스템 (FaceNet + YOLOv8-face) |
| 2025.09 | 캡스톤 디자인 페스티벌 장려상 | RPi5 기반 실시간 객체탐지 CCTV |

---

## 🛠 Tech Stack

**Firmware / Embedded**

![C](https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-A22846?style=for-the-badge&logo=raspberrypi&logoColor=white)
![STM32](https://img.shields.io/badge/STM32-03234B?style=for-the-badge&logo=stmicroelectronics&logoColor=white)
![ROS2](https://img.shields.io/badge/ROS2-22314E?style=for-the-badge&logo=ros&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Qt](https://img.shields.io/badge/Qt-41CD52?style=for-the-badge&logo=qt&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

| 분야 | 기술 |
|---|---|
| MCU | STM32 (HAL / CubeMX), STM32F103, STM32L4 |
| 통신 | CAN (bxCAN / MCP2515), UART, I2C, SPI, MQTT |
| OS / 시스템 | Linux, SocketCAN, 디바이스 드라이버, 멀티스레딩, ROS2 / micro-ROS |
| 라이브러리 | OpenCV, Qt Widgets, mosquittopp, libgpiod |
| 빌드 | STM32CubeIDE, GCC, CMake, Make |

---

## 📁 주요 프로젝트

### 1. [CATNIP — CAN 기반 분산 ECU 무인 배달 차량](https://github.com/kyoung-mo/can-based-autonomous-delivery-car)
> STM32 × 2 + Raspberry Pi × 3 분산 ECU 아키텍처 기반 무인 배달 RC카 (PM)
- CAN 250kbps 온보드 통신 (주행 / 미션 / 화물함 ECU 분리)
- OpenCV 라인트레이싱 + ArUco 마커 자율 주행
- PIN 인증 기반 화물함 제어 (STM32F103 + 키패드 + 서보)
- MQTT 실시간 관제 + Qt 주문 클라이언트

### 2. [자율주행 스마트 병동 관리 시스템](https://github.com/kyoung-mo/hospital-robot-ROS2)
> TurtleBot3 2대 기반 ROS2 멀티로봇 자율주행 시스템 (PM)
- ROS2 멀티 도메인 + Domain Bridge로 2-로봇 통신 구조 설계 및 통합
- micro-ROS 기반 OpenCR 주변장치(버튼 · RGB LED · LCD) 제어
- Whisper STT 음성 인터랙션 파이프라인 구현 (인식률 33% → 87% 개선)
- YOLO 영상 전송 최적화 (Raw → CompressedImage, 1fps → 24fps)

### 3. [STM32 Dam Control System](https://github.com/kyoung-mo/STM32-Dam-Control-System)
> STM32 기반 댐 제어 시스템 (DHT11 / 키패드 / 서보 / I2C LCD)
- HAL 기반 센서 드라이버 직접 작성 (DHT11 / I2C LCD / 4×4 키패드)
- ADC 수위 센서 기반 수문 자동 제어 로직
- UART 기반 실시간 데이터 로깅

### 4. [기능안전 기반 스마트 DMS (운전자 모니터링 시스템)](https://github.com/kyoung-mo/dms_functional_safety) *(진행 중)*
> AI 추론과 실시간 안전 기능을 물리적으로 분리한 투트랙 임베디드 시스템
- RPi5 + Hailo-8 NPU : 얼굴 검출 · 랜드마크 기반 졸음 판정 (AI 추론)
- STM32 + FreeRTOS : 우선순위 기반 실시간 안전 태스크 (Watchdog / CAN Tx / UART Rx)
- UART + Heartbeat로 두 시스템 연동, 통신 단절 시 CAN DTC 송출
- 관심사 분리 : AI의 비결정성이 안전 기능을 침해하지 못하도록 설계

---

## 📊 GitHub Stats

![kyoung-mo's GitHub stats](https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=kyoung-mo&theme=dark)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=kyoung-mo&layout=compact&theme=dark&hide_border=true)
