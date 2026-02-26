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
> **대규모 트래픽 환경에서 특정 노드에 부하가 집중되는 문제를 풀기 위한 커스텀 해싱 알고리즘 논문 프로젝트**

- **Period**: 2025.01 ~ 2026.02 (13개월)
- **Role**: 제1저자 (알고리즘 설계, 실험 설계·구현·분석, 논문 작성)
- **Tech Stack**: Python, Redis, Docker
- **Publication**: [📝 TIIS 2026 게재 예정 (SCIE)](https://doi.org/10.3837/tiis.2026.xx.xxx)
- **주요 성과**: NASA 웹 로그 테스트 결과, **기존 Consistent Hashing 대비 부하 불균형 33.8% 개선**

#### 핵심 로직
- **실시간 트래픽 분산**: LRU 카운터 기반 모니터링으로 Hot-key 발생 시 즉시 요청 경로를 바꿈
- **가용성 최적화**: Hot-key 승격 시 발생하는 성능 저하를 막기 위해 **Guard Phase** 및 **비동기 예열** 구조 도입
- **데이터 일관성 해결**: **Write-Primary** 정책을 적용해 분산 환경의 데이터 꼬임 및 정합성 이슈 해결

#### 트러블슈팅
- **해싱 및 메모리 효율 개선**: MD5 연산 병목을 `xxHash64`로 대체하고 `__slots__`를 적용해 **속도 20배 향상 및 메모리 50% 절감**
- **Latency Spike 대응**: 특정 키에 요청이 몰리는 환경(Zipfian)에서 **Guard Phase**로 캐시 미스 구간을 제어해 부하 분산 효율 개선
- **테스트 처리량(Throughput) 한계 극복**: I/O 블로킹 문제를 `ThreadPoolExecutor` 비동기 모델로 해결해 **180,000 OPS급 고부하 테스트 환경** 구축

👉 [**트러블슈팅 확인하기 →**](https://github.com/bh1848/D-HASH/blob/main/docs/REPORT_KR.md#5-트러블슈팅)

<br/>

### [⚖️ MySQL vs Redis 성능 비교 벤치마크](https://github.com/bh1848/mysql-redis-benchmark)
> **저장 매체(Disk vs Memory) 및 데이터 구조에 따른 쓰기/조회 성능 분석 논문 프로젝트**

- **Period**: 2023.10 ~ 2024.06 (9개월)
- **Role**: 제1저자 (실험 설계 및 분석)
- **Tech Stack**: Java, Spring Boot, MySQL, Redis
- **Publication**: [📜 JICS 2024 게재 (KCI)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)
- **주요 성과**: 연산 유형별 성능 차이(평균 7.8배)를 데이터로 증명해 캐시 도입의 기술적 근거 마련

#### 핵심 로직
- **벤치마크 환경 구축**: `AbstractBatchExperiment` 추상화로 측정 로직을 하나로 합치고, Connection Warm-up으로 초기 측정 오차 제거
- **Spring Profile 기반 환경 격리**: 테스트 대상 외의 Bean 생성을 막아 다른 서비스 간섭 없는 순수 시스템 성능 측정 환경 구축
- **데이터 구조별 성능 분석**: B-Tree(Disk)와 Hash(Memory) 구조 차이에 따른 배치 연산 성능 차이(Trade-off) 검증

#### 트러블슈팅
- **테스트 반복 실행 이슈 해결**: PK 충돌 및 인덱스 파편화를 막기 위해 `ddl-auto: create`와 전용 프로파일로 클린한 테스트 환경 유지
- **측정 정밀도 개선**: `System.currentTimeMillis()`의 한계를 대량 연산 후 산술 평균을 내는 방식으로 보완해 **0.17ms 단위 지표** 확보
- **병목 원인 파악**: 동기식 I/O의 Stop-and-Wait 구조 때문에 처리량이 떨어지는 것을 확인, 실무 관점의 **'Client Side Latency'를 핵심 지표로 채택**해 데이터 신뢰도 개선

👉 [**트러블슈팅 확인하기 →**](https://github.com/bh1848/mysql-redis-benchmark#4-트러블슈팅)

<br/>

## 💻 Projects

### [🌕 동구라미: 대학교 동아리 통합 관리 플랫폼](https://github.com/bh1848/USW-Circle-Link-Server)
> **교내 동아리 정보 파편화 문제를 해결하고 운영 효율을 높인 중앙 관리 시스템**

- **Period**: 2024.05 ~ 2025.03 (10개월)
- **Role**: Backend Developer (인증/보안 및 핵심 API 구현)
- **Tech Stack**: Java, Spring Boot, Spring Security, JPA/QueryDSL, MySQL, Redis, AWS (EC2/S3/RDS), Docker

#### 주요 작업 내용
- **인증 및 권한 구조 설계**: JWT와 Redis(RTR)를 조합한 보안 쿠키 전략으로 토큰 탈취를 방어하고, 도메인별 다중 권한 제어 로직 구현
- **DB 성능 최적화**: QueryDSL 동적 쿼리와 Bulk 연산을 적용해 N+1 문제를 해결하고 쿼리 실행 수 90% 이상 절감
- **리소스 효율 및 보안 강화**: S3 Presigned URL 도입으로 서버 부하를 줄이고, 파일 Magic Number 검증 로직으로 악성 파일 업로드 차단
- **운영 가시성 확보**: MDC 기반 로그 추적 시스템을 구축하여 분산 환경에서의 장애 대응 효율 개선

#### 트러블슈팅
- **다중 도메인 인증 로직 개선**: 책임 연쇄(CoR) 패턴을 도입해 복잡한 `if-else` 분기를 제거하고, 확장성 있는 인증 파이프라인으로 구조 변경
- **대량 데이터 삭제 성능 최적화**: JPQL 벌크 연산으로 쿼리 수를 획기적으로 줄이고(2N+2 → 고정 10), DB 삭제 시 S3 파일이 남지 않도록 로직 결합도 조정
- **파일 업로드 및 XSS 보안**: `Jsoup` 화이트리스트와 바이트 단위 검증 로직을 공통 인터셉터(@InitBinder)에 배치해 누락 없는 보안 환경 구축
- **CORS 환경 내 쿠키 전송 이슈 해결**: 브라우저 `SameSite` 정책 강화에 대응해 로우레벨 헤더 제어와 환경별 프로파일 이원화로 크로스 도메인 인증 문제 해결

👉 [**트러블슈팅 확인하기 →**](https://github.com/bh1848/USW-Circle-Link-Server#6-트러블슈팅)

<br/>

### [💬 수챗: 대학교 커뮤니티 기반 랜덤 채팅 서비스](https://github.com/bh1848/suchat-backend)
> **교내 구성원 인증 기반의 실시간 1:1 익명 채팅 서비스**

- **Period**: 2023.09 ~ 2024.09 (13개월)
- **Role**: Backend Developer (매칭 엔진 및 인증 구조 설계·구현)
- **Tech Stack**: Java, Spring Boot, Spring Security, MySQL, Redis, AWS, WebSocket

#### 주요 작업 내용
- **인증 및 보안 시스템 구축**: JWT와 Redis 블랙리스트를 조합해 로그아웃 시 토큰 재사용을 방지하고, 안전한 인증 파이프라인 구현
- **매칭 엔진 설계**: Redis ZSet 기반의 대기열 구조를 설계하여 매칭 시 발생하는 DB 부하를 줄이고 처리 속도 개선
- **비동기 알림 시스템**: `CompletableFuture`와 Redis Pub/Sub을 활용해 사용자에게 실시간으로 전달되는 논블로킹 알림 기능 구현
- **데이터 정합성 관리**: 임시 테이블 분리 및 스케줄러 기반 정제 로직을 도입해 메인 DB의 데이터 무결성 유지

#### 트러블슈팅
- **비동기 기반 분산 매칭 엔진**: 동기 방식의 매칭 처리 병목을 해결하기 위해, Redis ZSet과 `@Async`를 조합해 연산을 격리하고 처리 효율 개선
- **토큰 보안 강화**: JWT 탈취 리스크를 줄이기 위해 Access Token 수명을 단축하고, Redis TTL 기반의 Refresh Token 로테이션(RTR) 적용
- **유령 데이터 자동 정리**: 미인증 회원 데이터 누적으로 인한 리소스 낭비를 막기 위해, `@Scheduled` 기반의 배치 작업으로 주기적인 데이터 클리닝 로직 구축
- **매칭 상태 동기화 이슈**: 분산 환경에서 발생하는 매칭 상태 불일치를 해결하기 위해 Redis를 활용한 상태 공유 및 원자적(Atomic) 연산 적용

👉 [**트러블슈팅 확인하기 →**](https://github.com/bh1848/suchat-backend/#6-트러블슈팅)

<br/>

### [♻️ 요분정: AI 기반 쓰레기 분류 플랫폼](https://github.com/bh1848/yobunjung-backend)
> **AI 객체 인식 기술과 IoT 수거함을 결합한 스마트 분리배출 지원 서비스**

- **Period**: 2024.09 ~ 2024.11 (3개월)
- **Role**: Backend & AI Serving (백엔드 전 공정 및 AI 파이프라인 구축 전담)
- **Tech Stack**: Python, Flask, MySQL, ONNX, OpenCV, AWS

#### 주요 작업 내용
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

- **Period**: 2023.09 ~ 2023.11 (3개월)
- **Role**: Application Developer (메인 로직 및 비동기 파이프라인 구현)
- **Tech Stack**: Python, OpenCV, MediaPipe, PyQt5, Pygame

#### 주요 작업 내용
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
