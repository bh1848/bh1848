<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="banner" />
</p>

# 🐶 안녕하세요. 백엔드 개발자 방혁입니다. 

> **"단순한 구현 이상으로, 데이터에 기반해 성능을 개선하는 것과 안정적인 아키텍처를 지향합니다."**

사용자 경험을 최우선으로 생각하며, 특히 **대용량 트래픽 처리**와 **시스템 아키텍처**에 깊은 관심을 가지고 있습니다. 
- **Email:** bh1848@naver.com
- **Blog:** [hzeror.blog](https://bh1848.github.io/hzeror)

### 🥷 Skills
**Main (Product-Level)**
<p>
  <img src="https://img.shields.io/badge/Java-111827?style=flat-square&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring%20Boot-111827?style=flat-square&logo=springboot&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring%20Security-111827?style=flat-square&logo=springsecurity&logoColor=white" />
  <img src="https://img.shields.io/badge/JPA%2FHibernate-111827?style=flat-square&logo=hibernate&logoColor=white" />
  <img src="https://img.shields.io/badge/JUnit5-111827?style=flat-square&logo=junit5&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-111827?style=flat-square&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis-111827?style=flat-square&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-111827?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS-111827?style=flat-square&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-111827?style=flat-square&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Postman-111827?style=flat-square&logo=postman&logoColor=white" />
</p>

**Sub & Tools (Experience)**
<p>
  <img src="https://img.shields.io/badge/QueryDSL-0078D7?style=flat-square&logo=java&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white" />
  <img src="https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white" />
</p>

<br/>

## 🔬 Research

### [📊 D-HASH: Dynamic Hot-key Aware Scalable Hashing (SCIE)](https://github.com/bh1848/D-HASH)
> **대규모 트래픽 환경의 특정 키 집중 과부하 해결을 위한 동적 해싱 알고리즘 연구**

- **Period**: 2025.01 ~ 2026.02 (13개월)
- **Role**: 제1저자 (알고리즘 설계, 실험 설계·구현·분석, 논문 작성)
- **Tech Stack**: Python, Redis, Docker
- **Publication**: [📝 Paper (SCIE / TIIS 2026 예정)](https://doi.org/10.3837/tiis.2026.xx.xxx)

**주요 연구 내용**
- **동적 라우팅 시스템**: LRU 카운터 기반 Hot-key 실시간 감지 및 트래픽 분산 알고리즘 구현
- **Guard Phase 아키텍처**: Hot-key 승격 시 캐시 미스 방지를 위한 데이터 복제(Pre-warming) 메커니즘 설계
- **데이터 정합성 보장**: 읽기 분산 및 쓰기 중앙화(Write-Primary) 정책을 통한 데이터 일관성 유지
- **메모리 및 연산 최적화**: `xxHash` 적용 및 `__slots__` 메모리 최적화를 통한 고속 해싱 성능 확보

**연구 성과**
- NASA 웹 로그 실험 결과, 기존 Consistent Hashing 대비 **노드 간 부하 표준편차 33.8% 감소** 달성

**트러블슈팅**
- Python 내장 함수의 성능 한계로 인한 속도 저하를 **xxHash64 교체 및 `__slots__` 활용**으로 해결 [[상세보기]](https://bh1848.github.io/hzeror/D-HASH-python-hash-optimization/)
- 승격 직후 대체 노드 부재 문제를 **Guard Phase 도입 및 쓰기 병행 예열(Pre-warming)** 로직으로 해결 [[상세보기]](https://bh1848.github.io/hzeror/D-HASH-Hot-key-Promotion-Latency-Guard-Phase/)
- 분산 노드 간 정합성 문제를 **Write-Primary 정책**을 통해 구조적으로 해결 [[상세보기]](https://bh1848.github.io/hzeror/D-HASH-Write-Primary-Routing-Strategy/)
- 동기 I/O 요청 대기로 인한 측정 지연을 **ThreadPoolExecutor 비동기 부하 테스트**로 전환하여 측정 정밀도 확보 [[상세보기]](https://bh1848.github.io/hzeror/D-HASH-Asynchronous-Test-Environment/)

<br/>

### [⚖️ MySQL vs Redis 성능 비교 벤치마크 (KCI)](https://github.com/bh1848/mysql-redis-benchmark)
> **데이터 저장 방식(Disk vs Memory) 및 연산 유형에 따른 최적의 저장소 선정을 위한 정량적 비교 분석 연구**

- **Period**: 2023.10 ~ 2024.06 (9개월)
- **Role**: 제1저자 (실험 설계·구현·분석)
- **Tech Stack**: Java, Spring Boot, MySQL, Redis
- **Publication**: [📜 Paper (KCI / JICS 2024)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)

**주요 연구 내용**
- **벤치마크 환경 구축**: `AbstractBatchExperiment`로 측정 로직 공통화 및 Warm-up을 통한 초기 오차 배제
- **환경 격리 및 통제**: Spring Profile 활용 비대상 DB Bean 생성 차단으로 간섭 없는 독립적 실험 환경 조성
- **Disk vs Memory 정량 분석**: 10,000회 연산 및 네트워크 비용을 포함한 Latency 측정으로 B-Tree와 Hash 구조의 트레이드오프 검증

**연구 성과**
- Redis가 MySQL 대비 **평균 7.8배 빠른 속도**를 보임을 수치로 증명하여 캐싱 도입의 근거 마련

**트러블슈팅**
- 반복 테스트 시 PK 충돌 문제를 `ddl-auto: create` 옵션을 통한 실행 시점 초기화 로직으로 해결 [[상세보기]](/)
- 단건 조회 시 `0ms`로 측정되는 현상을 Batch 단위 총 소요 시간을 측정 후 평균을 역산하는 방식으로 해결 [[상세보기]](/)
- 동기식(Sync) 구조에 따른 Network RTT 병목을 확인하고, 지표를 'Client Side Latency'로 재정의하여 실험의 객관성 확보 [[상세보기]](/)

<br/>

## 💻 Projects

### [🌕 동구라미: 대학교 동아리 통합 관리 플랫폼](https://github.com/bh1848/USW-Circle-Link-Server)
> **교내 동아리 정보를 통합하고 관리 효율성을 높인 중앙 집중형 시스템**

- **Period**: 2024.05 ~ 2025.03 (10개월)
- **Role**: Backend Developer (핵심 로직 및 공통 컴포넌트 구현)
- **Tech Stack**: Java, Spring Boot, Spring Security, JPA, QueryDSL, MySQL, Redis, AWS EC2/S3/RDS, Docker

**주요 담당 업무**
- **인증 및 권한 관리**: `JWT + Redis(RTR)` 도입으로 토큰 탈취 위협을 완화하고, 도메인별 권한 검증 로직을 분리하여 유지보수성 확보
- **DB 성능 최적화**: `QueryDSL` 동적 쿼리 및 Bulk Delete 적용으로 N+1 문제를 해결하여 **쿼리 실행 수 90% 절감** (효율적인 데이터 로드 전략의 중요성을 체감함)
- **리소스 효율화 및 보안**: `S3 Presigned URL` 적용으로 서버 대역폭 절감 및 `Magic Number` 검증을 통한 악성 파일 업로드 방지
- **운영 가시성 확보**: `MDC` 기반 로그 추적 시스템 구축 및 환경별 로그 최적화를 통해 장애 대응 효율 제고

**트러블슈팅**
(작성 예정)

<br/>

### [💬 수챗: 랜덤 채팅 앱](https://github.com/bh1848/suchat-backend)
> **교내 구성원 인증 기반의 실시간 1:1 익명 랜덤 채팅 서비스**

- **Period**: 2023.09 ~ 2024.09 (13개월)
- **Role**: Backend Developer (매칭 엔진 및 인증 아키텍처 구축)
- **Tech Stack**: Java, Spring Boot, Spring Security, JPA, MySQL, Redis, AWS EC2, WebSocket, Async

**주요 담당 업무**
- **매칭 엔진**: `Redis ZSet` 기반 대기열 아키텍처 설계로 **DB 부하 제로(0)화** 달성 (확장성을 고려한 선제적 조치)
- **이벤트 비동기 처리**: `CompletableFuture`와 `Redis Pub/Sub`을 활용하여 Non-blocking 알림 시스템 구축
- **데이터 정합성 유지**: 임시 테이블 분리 및 스케줄러 기반 정화 로직 도입으로 메인 DB 무결성 확보

**트러블슈팅**
(작성 예정)

<br/>

### [♻️ 요분정: AI 기반 쓰레기 분류 플랫폼](https://github.com/bh1848/yobunjung-backend)
> **AI 객체 인식 기술과 IoT 수거함을 결합한 스마트 분리배출 지원 서비스**

- **Period**: 2024.09 ~ 2024.11 (3개월)
- **Role**: Backend & AI Serving (백엔드 전 공정 및 AI 파이프라인 구축 전담)
- **Tech Stack**: Python, Flask, MySQL, ONNX, OpenCV, AWS EC2

**주요 담당 업무**
- **AI 추론 최적화**: YOLO 모델의 `ONNX` 경량화 및 `OpenCV` 전처리 파이프라인 구축으로 CPU 환경 내 실시간성 확보
- **실시간 통신 인프라**: `SSE` 프로토콜 도입으로 하드웨어-앱 간 저지연 피드백 시스템 구현
- **동시성 제어**: `Lock` 기반의 Thread-Safe 상태 관리를 적용하여 비동기 통신 간 데이터 경합 방지

**트러블슈팅**
(작성 예정)

<br/>

### [🚗 딴짓 하지 말아줘: 졸음운전 방지 시스템](https://github.com/bh1848/drowsy-driving-prevention)
> **MediaPipe 안면 랜드마크 분석 기술을 활용한 실시간 운전자 상태 모니터링 및 경고 솔루션**

- **Period**: 2023.09 ~ 2023.11 (3개월)
- **Role**: Application Developer (메인 로직 및 비동기 파이프라인 구현)
- **Tech Stack**: Python, OpenCV, MediaPipe, PyQt5, Pygame

**주요 담당 업무**
- **데이터 파이프라인**: `MediaPipe` 분석 데이터 처리에 최적화된 이벤트 루프 설계 및 시스템 통합
- **비동기 성능 최적화**: `QTimer` 기반 비동기 프레임 처리로 UI 프리징 해결 및 실시간 응답성 확보
- **판단 알고리즘 고도화**: EAR 수치와 연속 프레임 카운팅 로직을 결합하여 판별 신뢰도 향상

**트러블슈팅**
(작성 예정)

<br/>

## 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
