<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="banner" />
</p>

# 🐶 안녕하세요. 백엔드 개발자 방혁입니다. 

> **"단순한 구현 이상으로, 데이터에 기반해 성능을 개선하는 것과 안정적인 아키텍처를 지향합니다."**

사용자 경험을 최우선으로 생각하며, 특히 **대용량 트래픽 처리**와 **시스템 아키텍처**에 깊은 관심을 가지고 있습니다. 
- **Email:** bh1848@naver.com
- **Blog:** [hzeror.blog](https://hzeror.netlify.app/)

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

### [📊 D-HASH: 분산 캐시 Hot-key 쏠림 해결을 위한 동적 해싱 알고리즘](https://github.com/bh1848/D-HASH)
> **대규모 트래픽 환경에서 특정 노드에 부하가 집중되는 문제를 풀기 위한 커스텀 해싱 알고리즘**

- **Period**: 2025.01 ~ 2026.02 (13개월) | **Role**: 제1저자 (알고리즘 설계, 실험 설계·구현·분석, 논문 작성)
- **Tech Stack**: Python, Redis, Docker
- **Publication**: [📝 TIIS 2026 게재 예정 (SCIE)](https://doi.org/10.3837/tiis.2026.xx.xxx)
- **핵심 성과**: NASA 웹 로그 기반 실험 결과, **기존 Consistent Hashing 대비 부하 불균형 33.8% 감소** 달성

#### 핵심 메커니즘
- **실시간 트래픽 라우팅 엔진**: LRU 카운터 기반 모니터링을 통해 Hot-key 발생 시 즉시 요청 경로를 분산하는 로직 구축
- **서비스 가용성 및 Cold Start 방지**: Hot-key 승격 시점의 성능 저하를 제어하기 위한 **Guard Phase** 및 **비동기 예열(Pre-warming)** 구조 도입
- **데이터 일관성 확보**: **Write-Primary** 정책을 적용하여 분산 환경 내 데이터 파편화 및 정합성 이슈 해결

#### 트러블슈팅
- **해싱 및 메모리 효율 개선**: MD5 연산 병목을 `xxHash64`로 대체하고 `__slots__`를 적용하여 **해싱 속도 20배 향상 및 메모리 50% 절감**
- **Hot-key 승격 시 Latency Spike 방어**: 특정 키 집중 부하(Zipfian) 환경에서 **Guard Phase**로 캐시 미스 구간을 제어하여 부하 분산 효율 확보
- **벤치마크 처리량 한계 극복**: 클라이언트 I/O 블로킹 문제를 `ThreadPoolExecutor` 비동기 모델로 해결하여 **180,000 OPS급 고부하 테스트 환경** 직접 구축

👉 [**트러블슈팅 확인하기 →**](https://github.com/bh1848/D-HASH/blob/main/docs/REPORT_KR.md#7-트러블-슈팅)

<br/>

### [⚖️ MySQL vs Redis 성능 비교 벤치마크 (KCI)](https://github.com/bh1848/mysql-redis-benchmark)
> **저장 매체(Disk vs Memory) 및 데이터 구조에 따른 쓰기/조회 성능 정량 분석**

- **Period**: 2023.10 ~ 2024.06 (9개월) | **Role**: 제1저자 (실험 설계 및 분석)
- **Tech Stack**: Java, Spring Boot, MySQL, Redis
- **Publication**: [📜 2024 JICS 게재 (KCI)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)
- **핵심 성과**: 연산 유형별 성능 차이(평균 7.8배)를 데이터로 입증하여 캐시 도입의 기술적 근거 확보

#### 핵심 메커니즘
- **벤치마크 프레임워크 구축**: `AbstractBatchExperiment` 추상화로 측정 로직을 공통화하고, Connection Warm-up을 통해 초기 측정 오차 제거
- **Spring Profile 기반 환경 격리**: 벤치마크 대상 외의 Bean 생성을 차단하여 타 서비스 간섭 없는 순수 시스템 성능 측정 환경 조성
- **데이터 구조별 레이턴시 분석**: 10,000건 이상의 배치 연산을 수행하며 B-Tree(Disk)와 Hash(Memory) 간의 성능 트레이드오프 검증

#### 트러블슈팅
- **테스트 멱등성 확보**: 반복 실행 시 PK 충돌 및 인덱스 파편화 문제를 해결하기 위해 `ddl-auto: create`와 전용 프로파일을 활용한 클린 테스트 환경 유지
- **측정 정밀도 개선**: `System.currentTimeMillis()`의 해상도 한계를 극복하고자 대량 연산 후 산술 평균을 도출하여 **0.17ms 단위의 유효 지표** 확보
- **병목 구간 파악**: 이론치 대비 낮은 처리량의 원인을 동기식 I/O의 **Stop-and-Wait 물리적 한계**로 분석하고, 실무 관점의 'Client Side Latency'를 핵심 지표로 채택

👉 [**자세한 트러블슈팅 확인하기 →**](https://github.com/bh1848/mysql-redis-benchmark#6-트러블-슈팅)

<br/>

## 💻 Projects

### [🌕 동구라미: 대학교 동아리 통합 관리 플랫폼](https://github.com/bh1848/USW-Circle-Link-Server)
> **교내 동아리 정보를 통합하고 관리 효율성을 높인 중앙 집중형 시스템**

- **Period**: 2024.05 ~ 2025.03 (10개월) | **Role**: Backend Developer (핵심 로직 및 공통 컴포넌트 구현)
- **Tech Stack**: Java, Spring Boot, Spring Security, JPA, QueryDSL, MySQL, Redis, AWS EC2/S3/RDS, Docker

#### 주요 담당 업무
- **인증/권한 아키텍처 전담**  
  Custom JWT Filter 및 `Redis(RTR)`·보안 쿠키 전략을 독자 설계하여 토큰 탈취를 방어하고, 다중 도메인 권한 제어 파이프라인 구축
- **DB 성능 최적화**  
  `QueryDSL` 동적 쿼리 및 Bulk Delete 적용으로 N+1 문제를 해결하여 쿼리 실행 수 90% 절감 (효율적인 데이터 로드 전략의 중요성을 체감함)
- **리소스 효율화 및 보안**  
  `S3 Presigned URL` 적용으로 서버 대역폭 절감 및 `Magic Number` 검증을 통한 악성 파일 업로드 방지
- **운영 가시성 확보**  
  `MDC` 기반 로그 추적 시스템 구축 및 환경별 로그 최적화를 통해 장애 대응 효율 제고

#### 트러블슈팅
- **다중 인증 파이프라인 설계**  
  책임 연쇄(CoR) 패턴과 예외 기반 제어 흐름을 도입하여 UUID 기반의 다중 도메인 인증 시 발생하는 `if-else` 분기를 제거하고 OCP 확보
- **데이터 삭제 성능 및 정합성 최적화**  
  JPQL 벌크 연산을 통해 쿼리 수를 90% 이상 절감($2N+2 \rightarrow$ 고정 10)하고, 의도적 계층 결합으로 S3 고아 파일 발생 리스크를 설계 단계에서 차단
- **전역 XSS 및 파일 업로드 보안 강화**  
  `Jsoup` 기반 커스텀 화이트리스트와 바이트 단위 `Magic Number` 직접 검증 로직을 시스템 입구(@InitBinder)에 배치하여 휴먼 에러를 배제한 보안 무결성 달성
- **크로스 도메인 인증 유지**  
  브라우저의 `SameSite` 정책 강화에 대응하기 위해 로우레벨 헤더 제어와 환경별 프로파일 정책 이원화 전략으로 CORS 환경 내 쿠키 전송 호환성 확보

👉 [**트러블슈팅 확인하기 →**](https://github.com/bh1848/USW-Circle-Link-Server#6-트러블-슈팅)

<br/>

### [💬 수챗: 랜덤 채팅 앱](https://github.com/bh1848/suchat-backend)
> **교내 구성원 인증 기반의 실시간 1:1 익명 랜덤 채팅 서비스**

- **Period**: 2023.09 ~ 2024.09 (13개월) | **Role**: Backend Developer (매칭 엔진 및 인증 아키텍처 구축)
- **Tech Stack**: Java, Spring Boot, Spring Security, JPA, MySQL, Redis, AWS EC2, WebSocket, Async

#### 주요 담당 업무
- **인증 보안 시스템 구축**  
  독자적으로 설계한 `JWT + Redis` 블랙리스트 전략으로 로그아웃 시 토큰 재사용을 차단하고, 무중단 서비스를 위한 인증 파이프라인 완성
- **매칭 엔진**
  `Redis ZSet` 기반 대기열 아키텍처 설계로 DB 부하 감소 (확장성을 고려한 선제적 조치)
- **이벤트 비동기 처리**  
  `CompletableFuture`와 `Redis Pub/Sub`을 활용하여 Non-blocking 알림 시스템 구축
- **데이터 정합성 유지**  
  임시 테이블 분리 및 스케줄러 기반 정화 로직 도입으로 메인 DB 무결성 확보

#### 트러블슈팅
- **비동기 기반 논블로킹 분산 매칭 엔진**  
  매칭 대기열 병목과 동기 처리의 레이턴시 한계를 극복하기 위해, `ZSet`(O(log N))을 활용한 분산 큐와 `@Async` 기반의 비동기 연산 격리(Isolation) 아키텍처 설계
- **하이브리드 토큰 보안 아키텍처**  
  JWT 탈취의 구조적 한계를 극복하기 위해 Access Token 수명을 단축하고, Redis TTL 기반의 Refresh Token 로테이션(RTR)을 적용하여 서버 통제권을 확보한 인증망 구축
- **더티 데이터(Ghost Data) 자동 클리닝 파이프라인**  
  미인증 유령 회원 누적으로 인한 스토리지 낭비 및 PK 충돌을 방지하기 위해, `@Scheduled` 기반 트랜잭션 배치를 도입하여 주기적 리소스 누수 차단
  
👉 [**트러블슈팅 확인하기 →**](https://github.com/bh1848/suchat-backend/#6-트러블-슈팅)

<br/>

### [♻️ 요분정: AI 기반 쓰레기 분류 플랫폼](https://github.com/bh1848/yobunjung-backend)
> **AI 객체 인식 기술과 IoT 수거함을 결합한 스마트 분리배출 지원 서비스**

- **Period**: 2024.09 ~ 2024.11 (3개월) | **Role**: Backend & AI Serving (백엔드 전 공정 및 AI 파이프라인 구축 전담)
- **Tech Stack**: Python, Flask, MySQL, ONNX, OpenCV, AWS EC2

#### 주요 담당 업무
- **AI 추론 최적화**  
  YOLO 모델의 `ONNX` 경량화 및 `OpenCV` 전처리 파이프라인 구축으로 CPU 환경 내 실시간성 확보
- **실시간 통신 인프라**  
  `SSE` 프로토콜 도입으로 하드웨어-앱 간 저지연 피드백 시스템 구현
- **동시성 제어**  
  `Lock` 기반의 Thread-Safe 상태 관리를 적용하여 비동기 통신 간 데이터 경합 방지

#### 트러블슈팅
(작성 예정)

<br/>

### [🚗 딴짓 하지 말아줘: 졸음운전 방지 시스템](https://github.com/bh1848/drowsy-driving-prevention)
> **MediaPipe 안면 랜드마크 분석 기술을 활용한 실시간 운전자 상태 모니터링 및 경고 솔루션**

- **Period**: 2023.09 ~ 2023.11 (3개월) | **Role**: Application Developer (메인 로직 및 비동기 파이프라인 구현)
- **Tech Stack**: Python, OpenCV, MediaPipe, PyQt5, Pygame

#### 주요 담당 업무
- **데이터 파이프라인**  
  `MediaPipe` 분석 데이터 처리에 최적화된 이벤트 루프 설계 및 시스템 통합
- **비동기 성능 최적화**  
  `QTimer` 기반 비동기 프레임 처리로 UI 프리징 해결 및 실시간 응답성 확보
- **판단 알고리즘 고도화**  
  EAR 수치와 연속 프레임 카운팅 로직을 결합하여 판별 신뢰도 향상

#### 트러블슈팅
(작성 예정)

<br/>

## 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
