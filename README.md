# 안녕하세요, 구영모입니다. 👋
**통신 프로토콜과 하드웨어-소프트웨어 경계면을 다루는 펌웨어 엔지니어를 준비하고 있습니다.**  
CAN 버스 신호 레벨 디버깅, RTOS 실시간 설계, 리눅스 커널 드라이버를 다뤄왔습니다.

[![Velog](https://img.shields.io/badge/Velog-20C997?style=for-the-badge&logo=velog&logoColor=white)](https://velog.io/@mommers/posts)

---

## About Me ✨

| 기간 | 활동 / 경력 | 주요 내용 |
|---|---|---|
| 2025.12 ~ 2026.07 | Intel Edge AI SW 아카데미 | Intel 9기 **기수 대표**, 주요 프로젝트 PM 2회, STM32 프로젝트 4회 |
| 2020.03 ~ 2026.02 | 강원대학교(춘천) 졸업 | 디지털회로실험 조교, 전기전자공학과 전공 동아리장 |
| 2025.02 ~ 2025.08 | 지능형시스템최적화 연구실 (학부연구생) | CAN 이상탐지, Hailo 엣지 AI 최적화 연구 |
| 2025.11 | IT대학 졸업작품 경진대회 장려상 | RPi5 + Hailo8 기반 얼굴 인식 출입 통제 시스템 |
| 2025.09 | 캡스톤 디자인 페스티벌 장려상 | RPi5 스마트 객체탐지 CCTV |

---

## 🛠 Tech Stack

**Firmware / Embedded**

![C](https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![STM32](https://img.shields.io/badge/STM32-03234B?style=for-the-badge&logo=stmicroelectronics&logoColor=white)
![FreeRTOS](https://img.shields.io/badge/FreeRTOS-6FBF3F?style=for-the-badge)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-A22846?style=for-the-badge&logo=raspberrypi&logoColor=white)
![ROS2](https://img.shields.io/badge/ROS2-22314E?style=for-the-badge&logo=ros&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Qt](https://img.shields.io/badge/Qt-41CD52?style=for-the-badge&logo=qt&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

| 분야 | 기술 |
|---|---|
| MCU | STM32 (HAL / CubeMX) — F103 / L475 / F411 / F746(OpenCR), ATmega128 |
| RTOS / OS | FreeRTOS, Linux, 커널 디바이스 드라이버, 멀티스레딩 |
| 통신 | CAN (bxCAN / MCP2515 / SocketCAN), UART, I2C, SPI, MQTT |
| 미들웨어 | ROS2 (Humble) / micro-ROS, Domain Bridge |
| 라이브러리 | OpenCV, Qt Widgets, mosquittopp |
| 빌드 / 협업 | STM32CubeIDE, GCC, Make, CMake, Git |

---

## 📁 주요 프로젝트

### 1. [가변 실내 PBV](https://github.com/kyoung-mo/pbv-cabin) (최종 프로젝트, 진행중)
> 4노드 분산 CAN 기반 가변 실내(Reconfigurable Cabin) 시스템 — RPi5 Supervisor + HMI 담당 (PM)
- 4노드 분산 CAN(500kbps) : RPi5 Supervisor + STM32 Zone ECU 3개, Vector CANdb++ DBC 설계(좌석 명령/상태 분리)
- 안전 인터록 : 입력 → 승인/거부 판정 → CAN 구동 단방향 흐름, 기어 P에서만 모드 전환 허용
- 9축 좌석 제어(앞 리클라인·회전 / 뒤 리클라인·슬라이드) + 4개 실내 모드 프리셋(주행·회의·Full-space·휴식)
- PySide6 + QtQuick3D 실시간 디지털 트윈 HMI(좌석 명령/피드백 3D 시각화, X-ray 차체·Ambient 모드)

### 2. [자율주행 기반 무인 배달 시스템](https://github.com/kyoung-mo/can-based-autonomous-delivery-car)
> 3개 노드 분산 ECU 아키텍처 기반 무인 배달 시스템 (PM)
- CAN 250kbps 온보드 통신 (주행 / 미션 / 화물함 ECU 분리)
- OpenCV 라인트레이싱 + ArUco 마커 자율 주행
- PIN 인증 기반 화물함 제어 (STM32F103 + 키패드 + 서보)
- MQTT 실시간 관제 + Qt 주문 클라이언트

### 3. [졸음운전 감지 · 중앙 관제 플랫폼](https://github.com/kyoung-mo/dms_functional_safety) 
> AI 추론과 실시간 안전 기능을 물리적으로 분리한 투트랙 임베디드 시스템
- RPi5 + Hailo-8 NPU : 얼굴 검출 · 랜드마크 기반 졸음 판정 (AI 추론)
- STM32 + FreeRTOS : 우선순위 기반 실시간 안전 태스크 (Watchdog / CAN Tx / UART Rx)
- UART + Heartbeat(100ms)로 두 시스템 연동, 통신 단절(500ms Timeout) 시 CAN DTC 송출
- 관심사 분리 : AI의 비결정성이 안전 기능을 침해하지 못하도록 설계

### 4. [스마트 병동 관리 시스템](https://github.com/kyoung-mo/hospital-robot-ROS2)
> TurtleBot3 2대 기반 ROS2 멀티로봇 자율주행 시스템 (PM)
- ROS2 멀티 도메인 + Domain Bridge로 2-로봇 통신 구조 설계 및 통합
- micro-ROS 기반 OpenCR 주변장치(버튼 · RGB LED · LCD) 제어
- Whisper STT 음성 인터랙션 파이프라인 구현
- YOLO 영상 전송 최적화 (Raw → CompressedImage, 1fps → 24fps)

### 5. [댐 관리·제어 시스템](https://github.com/kyoung-mo/STM32-Dam-Control-System)
> STM32 기반 댐 제어 시스템 (DHT11 / 키패드 / 서보 / I2C LCD)
- HAL 기반 DHT11 / I2C LCD / 4×4 키패드 드라이버 설계 및 디버깅
- ADC 수위 센서 기반 수문 자동 제어 로직
- UART 기반 실시간 데이터 로깅

### 6. [얼굴 인식 출입 통제 시스템](https://github.com/kyoung-mo/face-security-system)
> RPi5 + Hailo-8 NPU 기반 경량 딥러닝 실시간 얼굴 인식 출입 장치 (학부 졸업작품, 장려상)
- 듀얼 모델(YOLOv8-face + FaceNet)을 단일 Hailo-8 디바이스에서 운용
- ONNX → HEF 변환 툴체인 구성(convert_to_hailo.sh), 추론 인터페이스를 CPU/Hailo 공통으로 추상화
- CPU 대비 Hailo 추론 성능(FPS·Latency) 벤치마크로 엣지 가속 효과 정량 측정
- Hailo 디바이스에서 두 모델을 공유 운용(VDevice)해 디바이스 점유 충돌 해소

### 7. [DS1302 RTC 리눅스 디바이스 드라이버](https://github.com/kyoung-mo/ds1302-linux-device-driver)
> GPIO Bit-banging 기반 3-wire 프로토콜을 구현한 커널 캐릭터 디바이스 드라이버
- alloc_chrdev_region + udev 자동 노드 생성, platform driver/device 구조
- Burst Read(0xBF)로 시간 레지스터 일괄 수신, mutex 기반 단일 오픈
- RPi5 커널 GPIO 번호 체계(RP1) 트러블슈팅

### 8. [ATmega128 베어메탈 엘리베이터](https://github.com/kyoung-mo/atmega128-elevator)
> 학부 2학년(2021), HAL 없이 레지스터 직접 제어로 구현한 3층 엘리베이터
- INT4/5/6 외부 인터럽트 + 디바운싱, Timer0 Fast PWM 모터 제어
- (목표층−현재층) 차이값 하나로 방향·거리를 결정하는 이동 로직

---

## 📊 GitHub Stats

![kyoung-mo's GitHub stats](https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=kyoung-mo&theme=dark)
![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=kyoung-mo&layout=compact&theme=dark&hide_border=true)
