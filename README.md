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
  <img src="https://img.shields.io/badge/JUnit5-25A162?style=flat-square&logo=junit5&logoColor=white" />
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
- **동적 라우팅 시스템 설계**: LRU 카운터 기반 **Hot-key 실시간 감지 알고리즘**을 구축하여 특정 노드에 쏠리는 트래픽을 지능적으로 분산
- **Guard Phase 아키텍처 도입**: Hot-key 승격 시 즉각 분산 대신 **Pre-warming(데이터 복제)** 기간을 두어 분산 환경의 초기 캐시 미스 문제를 엔지니어링적으로 해결
- **데이터 정합성 보장 전략**: 읽기 트래픽은 분산하되 쓰기 작업은 항상 Primary Node를 경유하는 **Write-Primary 정책**으로 분산 노드 간 데이터 불일치 원천 차단
- **메모리 및 연산 최적화**: Python 클래스 내 `__slots__` 선언으로 객체 메모리 점유율을 줄이고, `xxHash`를 적용하여 고속 해싱 처리 성능 확보

**연구 성과**
- NASA 웹 로그 및 Zipfian 분포 기반 실험 결과, 기존 Consistent Hashing 대비 **노드 간 부하 표준편차(Load Std Dev) 33.8% 감소** 달성

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
- **객체 지향적 벤치마크 프레임워크 설계**: `AbstractBatchExperiment` 추상 클래스를 정의하여 워밍업 및 시간 측정 로직을 중앙화하고, DB별 구현체(`MysqlBatchExperiment`, `RedisBatchExperiment`)가 실제 연산만 수행하도록 설계하여 측정 오차 제거
- **리소스 격리 및 환경 통제**: Spring Profile 기능을 활용해 테스트 대상이 아닌 DB의 Bean 생성을 차단(`autoconfigure.exclude`)하여 메모리 및 Connection Pool 간섭을 원천 방지
- **CRUD 시나리오 기반 정량 분석**: 동일한 비즈니스 로직 하에 10,000회의 Single Operation을 반복 수행하여, 디스크 기반 B-Tree(MySQL)와 인메모리 기반 Hash(Redis)의 Latency 차이를 정밀하게 측정
- **성능-안정성 트레이드오프 검증**: 연산별 시간 복잡도(O(log N) vs O(1))가 실제 애플리케이션 Latency(Serialization + Network I/O 포함)에 미치는 영향을 수치로 증명

**연구 성과**
- **평균 7.8배의 성능 격차 규명**: Redis가 MySQL 대비 평균 7.8배(1.39ms vs 0.17ms) 빠른 Latency를 기록함을 입증했으며, 특히 Delete 연산에서 최대 12.3배의 성능 우위 확인

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
- **확장형 인증 시스템**: `JWT + Redis(RTR)` 기반 아키텍처를 설계하여 **다중 도메인(Admin/Leader/User) 권한 위계를 객체지향적으로 격리**하고 토큰 재사용 공격 차단
- **DB 성능 최적화**: `QueryDSL` 동적 쿼리 및 `Bulk Delete`를 구현하여 **연관 데이터 삭제 시 발생하는 N+1 문제를 해결**하고 쿼리 실행 수 90% 감소
- **보안 및 운영 가시성**: `S3 Presigned URL`과 `Magic Number` 검증으로 자원 효율을 높이고, `MDC` 로그 추적 시스템을 구축하여 장애 대응 효율 제고

**트러블슈팅**
(작성 예정)

<br/>

### [💬 수챗: 랜덤 채팅 앱](https://github.com/bh1848/suchat-backend)
> **교내 구성원 인증 기반의 실시간 1:1 익명 랜덤 채팅 서비스**

- **Period**: 2023.09 ~ 2024.09 (13개월)
- **Role**: Backend Developer (매칭 엔진 및 인증 아키텍처 구축)
- **Tech Stack**: Java, Spring Boot, Spring Security, JPA, MySQL, Redis, AWS EC2, WebSocket, Async

**주요 담당 업무**
- **실시간 매칭 엔진**: `Redis Sorted Set(ZSet)` 기반 대기열 아키텍처를 설계하여 **초당 발생하는 매칭 트래픽의 DB 부하를 0으로 최적화**
- **비동기 이벤트 처리**: `CompletableFuture`와 `Redis Pub/Sub`을 활용해 **서버 스레드 점유 없이 실시간 매칭 알림**을 전달하는 비동기 구조 구현
- **인증 및 데이터 정합성**: `JWT + Redis TTL` 기반 블랙리스트 체계로 보안을 강화하고, 스케줄러 기반 미인증 데이터 정화로 **메인 DB의 인덱스 효율 유지**

**트러블슈팅**
(작성 예정)

<br/>

### [♻️ 요분정: AI 기반 쓰레기 분류 플랫폼](https://github.com/bh1848/yobunjung-backend)
> **AI 객체 인식 기술과 IoT 수거함을 결합한 스마트 분리배출 지원 서비스**

- **Period**: 2024.09 ~ 2024.11 (3개월)
- **Role**: Backend & AI Serving (백엔드 전 공정 및 AI 파이프라인 구축 전담)
- **Tech Stack**: Python, Flask, MySQL, ONNX, OpenCV, AWS EC2

**주요 담당 업무**
- **AI 서빙 최적화**: YOLO 모델의 **ONNX 변환 및 경량화 서빙**으로 CPU 환경 추론 속도 최적화 및 OpenCV 기반 이미지 전처리 파이프라인 구축
- **실시간 통신 인프라**: **SSE(Server-Sent Events)** 프로토콜을 도입하여 하드웨어(아두이노)-서버-앱 간의 실시간 분류 결과 피드백 시스템 구현
- **동시성 및 정합성 제어**: `Lock` 및 `Event` 기반의 **Thread-Safe 상태 관리**로 비동기 하드웨어 통신 중 데이터 경합 및 중복 요청 방지

**트러블슈팅**
(작성 예정)

<br/>

### [🚗 딴짓 하지 말아줘: 졸음운전 방지 시스템](https://github.com/bh1848/drowsy-driving-prevention)
> **MediaPipe 안면 랜드마크 분석 기술을 활용한 실시간 운전자 상태 모니터링 및 경고 솔루션**

- **Period**: 2023.09 ~ 2023.11 (3개월)
- **Role**: Application Developer (메인 로직 및 비동기 파이프라인 구현)
- **Tech Stack**: Python, OpenCV, MediaPipe, PyQt5, Pygame

**주요 담당 업무**
- **실시간 데이터 파이프라인**: `MediaPipe` 랜드마크 데이터를 시스템에 통합하고, 초당 프레임(FPS) 처리에 최적화된 **메인 이벤트 루프 및 스트리밍 구조 구축**
- **비동기 성능 최적화**: `QTimer` 기반의 비동기 프레임 처리 방식을 도입하여 **영상 분석 중 발생하는 UI 프리징 현상을 해결**하고 시스템의 실시간 응답성 확보
- **판단 알고리즘 시스템화**: EAR(Eye Aspect Ratio) 수치 분석 기반의 **연속 프레임 카운팅 로직**을 구현하여 실시간 상태 판별의 신뢰도 향상

**트러블슈팅**
(작성 예정)

<br/>

## 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
