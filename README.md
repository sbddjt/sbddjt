# Hello, I'm Seong Yun Jo 👋

<div align="left">
  <p>
    <b>"데이터가 생성되고, 처리되고, 활용되는 흐름을 직접 만들어보는 엔지니어입니다."</b><br>
    Python 기반 데이터 가공부터 Kafka 실시간 데이터 파이프라인, DB 설계와 클라우드 환경의 배포까지 경험하며<br>
    문제가 발생했을 때 데이터와 처리 흐름을 따라 원인을 찾고 해결하는 과정을 좋아합니다.
  </p>
</div>

---

## 👨‍💻 About Me

### 🎓 홍익대학교 컴퓨터공학과
* 4학년 휴학 중
* 운영체제, 네트워크, 데이터베이스, 알고리즘 등 CS 전공 이수

### 🚗 현대오토에버 모빌리티 SW 스쿨 3기 — Cloud Track
* Python, Linux, Database, Docker, Kubernetes, CI/CD 학습
* 차량 데이터 수집·저장 및 클라우드 기반 서비스 프로젝트 수행
* **Connected Car Telemetry 프로젝트 우수상**

### 📊 BDAI 13기 — 정규학회원
* 데이터 엔지니어링 기초 학습
* n8n을 활용한 API 연동 및 데이터 워크플로우 자동화 실습

<br>

## 🛠️ Tech & Experience

**Data & Programming**
<br>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/SQL-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white"/>
<img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white"/>

**Data Engineering**
<br>
<img src="https://img.shields.io/badge/Apache Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white"/>
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white"/>
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>
<img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white"/>

**Backend & Cloud**
<br>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white"/>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white"/>
<img src="https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white"/>

**ML & Visualization**
<br>
<img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white"/>
<img src="https://img.shields.io/badge/Keras-D00000?style=flat-square&logo=keras&logoColor=white"/>
<img src="https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=python&logoColor=white"/>

<br>

## 📦 Projects

### 📡 [Connected Car Telemetry](https://github.com/sbddjt/Connected-Car-Telemetry)
> 실시간 차량 데이터를 수집하고 이력 데이터와 최신 상태를 분리해 저장·조회하는 데이터 파이프라인

**현대오토에버 모빌리티 SW 스쿨 · 4인 팀 · 우수 프로젝트상**

```text
Dummy Car
    ↓
FastAPI Ingest API
    ↓
Apache Kafka
    ├── MongoDB Consumer → MongoDB (운행 이력)
    └── Redis Consumer   → Redis (최신 상태)
                              ↓
                         Query API
```

* FastAPI에서 차량 텔레메트리 데이터를 수신해 **Kafka Topic으로 발행하는 Command 경로 구현**
* Kafka Consumer를 통해 **MongoDB에 운행 이력 데이터 저장**
* MongoDB와 Redis Consumer의 목적에 맞게 **Consumer Group을 분리하여 데이터 소비 문제 해결**
* MongoDB는 누적 이력, Redis는 최신 상태를 저장하도록 역할 분리
* Kubernetes 리소스를 **Helm Chart로 구성**하고 서비스 배포 및 HPA 동작 검증

**Tech**  
`Python` `FastAPI` `Kafka` `MongoDB` `Redis` `Docker` `Kubernetes` `Helm`

---

### 🚨 PIR 센서 기반 실시간 낙상 감지
> 센서 시계열 데이터의 오탐 원인을 데이터 구성에서 찾고 학습 데이터를 보완한 머신러닝 프로젝트

**기계학습기초 · 4인 팀**

* 초기 검증에서 **정상 행동 40건 중 7건을 낙상으로 오인**하는 문제 확인
* 모델 수정에 앞서 학습 데이터를 분석하고, 낙상과 유사한 정상 행동 데이터 부족을 원인으로 판단
* 정지 상태 및 움직임 후 정지 상황 등 **비낙상 데이터 50건을 추가 수집·라벨링**
* NumPy를 활용해 잡음 추가, 시간축 이동, 속도 및 파형 크기 변화 등 **시계열 데이터 증강 구현**
* Pandas로 여러 CSV 데이터를 통합하고 학습용 데이터셋 구성
* TensorFlow/Keras로 모델을 재학습하고 Matplotlib으로 결과 검증
* 최종 테스트에서 **오탐률 3.3%**, 낙상 **Recall 95.1%** 기록

**Tech**  
`Python` `NumPy` `Pandas` `TensorFlow` `Keras` `Matplotlib`

---

### 🚘 [Car Pay-in](https://github.com/sbddjt/CarPayIn)
> 차량에서 QR 로그인부터 카드 등록, 입차, 결제, 출차까지 처리하는 차량 내 주차 결제 플랫폼

**현대오토에버 모빌리티 SW 스쿨 · 5인 팀 · 팀장**

```text
AAOS App
    ↓
Car Pay-in Backend
    ↓
PMS → PG / Card
    ↓
AWS IoT Core → Vehicle
```

* 팀장으로서 요구사항을 정리하고 **차량 앱·Backend·PMS·PG·카드사 간 서비스 및 데이터 흐름 설계**
* Python/FastAPI 기반 Car Pay-in Backend와 Mock PMS·PG·Card 서비스 구현 및 연동
* 사용자·차량·주차 세션·결제 이력의 데이터 관계 및 저장 구조 설계
* QR 기반 로그인과 현대 OAuth를 연계한 차량 등록 흐름 구성
* SQS·Lambda·IoT Core를 활용한 비동기 이벤트 및 차량 알림 흐름 구현
* 유스케이스, API 명세, 시퀀스 다이어그램과 테스트 기준을 문서화해 협업 기준 정리

**Tech**  
`Python` `FastAPI` `PostgreSQL` `Redis` `AWS` `Docker` `Kotlin`

<br>

## 📚 Currently Learning

* **Data Engineering** — Python·SQL 기반 데이터 처리와 데이터 파이프라인 기본기 강화
* **Streaming** — Kafka Producer/Consumer, Partition, Consumer Group 및 장애 상황 학습
* **Workflow Automation** — n8n과 외부 API를 활용한 데이터 수집·가공 자동화
* **CS Fundamentals** — 학습한 개념을 코드와 기술 블로그로 꾸준히 정리

<br>

## 🏅 Certifications

* **SQLD** — SQL Developer
* **Linux Master Level 2**
* **OPIc IH**

<br>

## 📝 Learning & 기록

새롭게 공부한 내용을 직접 실습하고 정리하며 기록하고 있습니다.

* [Velog 기술 블로그](https://velog.io/@sbddjt/posts)
* [Kafka 파티션 구성과 브로커 장애 복구 실험](https://velog.io/@sbddjt/Connected-Car-Telemetry-재구성기-2)
* [SQLite 영속 버퍼와 Producer 재전송 구현](https://velog.io/@sbddjt/Connected-Car-Telemetry-재구성기-3)

<br>

## 📫 Contact

* **Email**: sbddjt16@naver.com
* **GitHub**: [github.com/sbddjt](https://github.com/sbddjt)
* **Velog**: [velog.io/@sbddjt](https://velog.io/@sbddjt/posts)

<br>

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=sbddjt&label=Visitors&color=3776AB&style=flat-square" alt="Visitors" />
</div>
