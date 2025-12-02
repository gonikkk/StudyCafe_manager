# 스터디 카페 관리 시스템
# Study Cafe Manager
스터디 카페 IoT 기반 좌석 관리 시스템

## 프로젝트 소개
저비용 IoT 기반으로 스터디 카페 좌석을 자동 관리하는 시스템입니다.
좌석 예약/일시정지/종료, 환경 센서 데이터(온도·습도·소음) 수집,
관리자 웹 페이지 제어, STM32 LCD 실시간 상태 표시 기능을 제공합니다.

## 개발 기간
* 25.09.24 ~ 25.10.22

## 멤버 구성
| 이름 | 담당 |
|------|------|
| 김선곤 | Bluetooth–STM32 연동, LCD 표시, 시스템 통합 |
| 김영교 | DB 구조 설계, phpMyAdmin 웹 제어, 서버 구축 |

## 개발 환경
- Raspberry Pi (MariaDB + Server)
- STM32 Nucleo-F411RE
- C Language
- Bluetooth HC-05
- ESP8266
- LCD1602 (I2C)
- 온습도·소음 센서

## 주요 기능

### 좌석 관리
- OPEN / FULL / PAUSE 상태 표시
- 좌석 예약 시작 및 종료
- 시간 연장 기능
- 일시정지(PAUSE) 기능

### 환경 모니터링
- 온도, 습도, 소음 수집
- LCD 2행에 환경 정보 표시

### 관리자 기능
- phpMyAdmin 웹 UI 기반 제어
- DB 수정 시 STM32 LCD 즉시 반영
- 예약, 좌석 상태 데이터 관리

### 통신 구조
- 센서 → 서버 → DB
- DB → IoT 서버 → Bluetooth → STM32 → LCD
- 라즈베리파이를 중심으로 실시간 동기화되는 구조

## 파일 구조
code/

    iot_client_Bluetooth/
        build_bt.sh
        iot_client_bluetooth
        iot_client_bluetooth.c

    iot_server/
        Makefile
        idpasswd.txt
        iot_client
        iot_client.c
        iot_server
        iot_server.c

    sql_client/
        Makefile
        iot_client_sensor_device
        iot_client_sensor_device.c

    nucleo_f411re_uart2_printf_uart.zip
    studycafe_bluetooth.zip
    README.md
    studycafe.pptx
