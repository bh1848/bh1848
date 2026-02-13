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
  <img src="https://img.shields.io/badge/JUnit5-25A162?style=flat-square&logo=junit5&logoColor=white" />
</p>

<br/>

## 🔬 Research

### [📊 D-HASH: Dynamic Hot-key Aware Scalable Hashing (SCIE)](https://github.com/bh1848/D-HASH)
> **개요:** 대규모 트래픽 환경에서 특정 키에 요청이 집중될 때 발생하는 단일 노드 과부하 문제 해결을 위한 알고리즘 개발  
> **성과:** 독자적인 동적 라우팅 알고리즘을 개발하여 Consistent Hashing 대비 부하 표준편차 33.8% 감소  
> **스택:** Python, Redis, Docker    
> **역할:** 제1저자 (알고리즘 설계, 실험 설계·구현·분석, 논문 작성)  
> **논문:** [📝 Paper (SCIE / TIIS 2026)](https://doi.org/10.3837/tiis.2026.xx.xxx)

- **동적 라우팅 알고리즘 설계 (Window-Based Routing)**
  - **문제:** 단순히 요청을 분산하면 캐시 미스가 발생하거나 데이터 정합성이 깨짐.
  - **해결:**
    - **승격 로직:** LRU 카운터를 통해 요청 빈도가 임계값(T)을 넘는 키를 실시간 감지하여 Hot-key로 승격.
    - **Guard Phase 도입:** 승격 직후 바로 트래픽을 분산하지 않고, 일정 윈도우(W) 동안은 데이터를 복제(Pre-warming)하는 **Guard Phase**를 두어 초기 캐시 미스를 방지했습니다.
    - **결정론적 라우팅:** 랜덤 방식 대신 요청 횟수 기반의 윈도우 스위칭 기법을 적용하여, 메인 노드와 대체 노드 간의 부하를 결정론적으로 분배했습니다.

- **데이터 정합성 및 성능 최적화**
  - **Write-Primary 정책:** 읽기 요청은 분산하되, 쓰기/수정 요청은 항상 **Primary Node**로만 향하게 하여 분산 환경에서의 데이터 파편화를 방지했습니다.
  - **Python 최적화:** `xxHash` 라이브러리를 적용하여 해싱 속도를 높이고, 클래스에 `__slots__`를 선언하여 대량의 키 객체 생성 시 **메모리 사용량을 최적화**했습니다.

- **정량적 성과**
  - NASA 웹 로그 및 Zipfian 분포 데이터셋 실험 결과, 기존 Consistent Hashing 대비 **서버 간 부하 표준편차(Load Std Dev) 33.8% 감소**를 달성하여 시스템 안정성을 입증했습니다.

<br/>

### [⚖️ MySQL vs Redis 성능 비교 벤치마크 (KCI)](https://github.com/bh1848/mysql-redis-benchmark)
> **개요:** 데이터의 성격과 연산 유형에 따른 최적의 저장소를 선정하기 위한 정량적 비교 분석 연구  
> **성과:** 대량 데이터 처리 시 Redis가 MySQL 대비 평균 7.8배(1.39ms vs 0.17ms) 빠름을 입증  
> **스택:** Java, Spring Boot, MySQL, Redis    
> **역할:** 제1저자 (실험 설계·구현·분석)    
> **논문:** [📜 Paper (KCI / JICS 2024)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)

- **객체 지향적 벤치마크 프레임워크 설계**
  - **템플릿 메서드 패턴 적용:** 공정한 비교를 위해 `AbstractBatchExperiment` 추상 클래스를 정의하여 측정 로직(타이머, 반복 횟수 등)을 통일하고, DB별 구현체(`MysqlBatchExperiment`, `RedisBatchExperiment`)가 실제 연산만 수행하도록 설계했습니다.
  - **대량 데이터 배치 처리:** 단건 처리가 아닌 **Batch Processing** 성능을 검증하기 위해 대용량 데이터의 일괄 삽입(Insert), 조회(Select), 수정(Update), 삭제(Delete) 시나리오를 구현했습니다.

- **정량적 데이터 분석 및 성과**
  - **성능 격차 규명:** 실험 결과, 단순 Key-Value 조회 시 Redis가 MySQL(Disk I/O 기반) 대비 **평균 7.8배(1.39ms vs 0.17ms) 빠른 응답 속도**를 보임을 입증했습니다.
  - **아키텍처 제언:** 쓰기(Write) 연산이 빈번한 환경과 읽기(Read) 위주의 환경에서의 성능 변화 추이를 분석하여, **데이터의 정합성이 중요한 원장 데이터는 MySQL에, 빈번한 조회 데이터는 Redis에 위임**하는 하이브리드 아키텍처의 수치적 근거를 마련했습니다.

<br/>

## 💻 Projects

### [🌕 동구라미: 대학교 동아리 통합 관리 플랫폼](https://github.com/bh1848/USW-Circle-Link-Server)
> **교내 동아리 정보를 통합하고 관리 효율성을 높인 중앙 집중형 시스템**

- **기간**: 2024.05 ~ 2025.03 (10개월)
- **역할**: Backend Developer (핵심 로직 및 공통 컴포넌트 구현)
- **기술**: Java, Spring Boot, Spring Security, JPA, QueryDSL, MySQL, Redis, AWS EC2/S3/RDS, Docker

**주요 담당 업무**
- **확장형 인증 시스템**: `JWT + Redis(RTR)` 기반 아키텍처를 설계하여 **다중 도메인(Admin/Leader/User) 권한 위계를 객체지향적으로 격리**하고 토큰 재사용 공격 차단
- **DB 성능 최적화**: `QueryDSL` 동적 쿼리 및 `Bulk Delete`를 구현하여 **연관 데이터 삭제 시 발생하는 N+1 문제를 해결**하고 쿼리 실행 수 90% 감소
- **보안 및 자원 효율화**: `S3 Presigned URL` 도입으로 서버 I/O 점유를 방지하고, `Magic Number` 기반 바이너리 검증으로 **비정상 파일 업로드 원천 차단**
- **운영 가시성 확보**: `MDC` 기반 로그 추적 시스템 구축 및 **4xx 필터링 등으로 운영 환경 로그 최적화**를 통해 장애 대응 효율성 제고

**[트러블슈팅]**
- [Bulk 연산 후 영속성 컨텍스트 불일치 문제 해결](https://github.com/bh1848/USW-Circle-Link-Server#trouble-shooting-1)

<br/>

### [💬 수챗: 랜덤 채팅 앱](https://github.com/bh1848/suchat-backend)
> **교내 구성원 인증 기반의 실시간 1:1 익명 랜덤 채팅 서비스**

- **기간**: 2023.09 ~ 2024.09 (13개월)
- **역할**: Backend Developer (매칭 엔진 및 인증 아키텍처 구축)
- **기술**: Java, Spring Boot, Spring Security, JPA, MySQL, Redis, AWS EC2, WebSocket, Async

**주요 담당 업무**
- **실시간 매칭 엔진**: `Redis Sorted Set(ZSet)` 기반 대기열 아키텍처를 설계하여 **초당 발생하는 매칭 트래픽의 DB 부하를 0으로 최적화**
- **인증 보안 시스템**: `JWT + Redis` 기반 인증 체계를 구축하고, 로그아웃 시 **토큰 블랙리스트(TTL)** 처리로 인증 정보의 재사용 가능성을 원천 차단
- **비동기 이벤트 처리**: `CompletableFuture`와 `Redis Pub/Sub`을 활용해 **서버 스레드 점유 없이 실시간 매칭 알림**을 전달하는 비동기 구조 구현
- **데이터 정합성 확보**: `Member-MemberTemp` 테이블 분리 설계와 스케줄러 기반 미인증 데이터 정화로 **메인 DB의 인덱스 효율 및 무결성 유지**

**[트러블슈팅]**
- 다중 사용자의 동시 매칭 요청 시 발생하는 레이스 컨디션을 Redis의 원자적 연산을 활용해 해결

<br/>

### [♻️ 요분정: AI 기반 쓰레기 분류 플랫폼](https://github.com/bh1848/yobunjung-backend)
> **AI 객체 인식 기술과 IoT 수거함을 결합한 스마트 분리배출 지원 서비스**
- **기간**: 2024.09 ~ 2024.11 (3개월)
- **역할**: Backend & AI Serving (백엔드 전 공정 및 AI 파이프라인 구축 전담)
- **기술**: Python, Flask, MySQL, ONNX, OpenCV, AWS EC2

**주요 담당 업무 및 성과**
- **AI 서빙 최적화**: YOLO 모델의 **ONNX 변환 및 경량화 서빙**으로 CPU 환경 추론 속도 최적화 및 OpenCV 기반 이미지 전처리 파이프라인 구축
- **실시간 통신 인프라**: **SSE(Server-Sent Events)** 프로토콜을 도입하여 하드웨어(아두이노)-서버-앱 간의 실시간 분류 결과 피드백 시스템 구현
- **동시성 및 정합성 제어**: `Lock` 및 `Event` 기반의 **Thread-Safe 상태 관리**로 비동기 하드웨어 통신 중 데이터 경합 및 중복 요청 방지
- **아키텍처 및 인프라**: Flask Blueprint 기반의 도메인 모듈화 설계 및 **AWS EC2/RDS 인프라 직접 구축/운영**을 통한 서비스 안정성 확보

**[트러블슈팅]**
- AI 모델 추론 병목 해결을 위해 ONNX Runtime 도입 및 이미지 채널(HWC→CHW) 변환 최적화로 응답 속도 개선

<br/>

### [🚗 딴짓 하지 말아줘: 졸음운전 방지 시스템](https://github.com/bh1848/drowsy-driving-prevention)
> **MediaPipe 안면 랜드마크 분석 기술을 활용한 실시간 운전자 상태 모니터링 및 경고 솔루션**
- **기간**: 2023.09 ~ 2023.11 (3개월)
- **역할**: Application Developer (메인 로직 및 비동기 파이프라인 구현)
- **기술**: Python, OpenCV, MediaPipe, PyQt5, Pygame

**주요 담당 업무 및 성과**
- **실시간 데이터 파이프라인**: `MediaPipe` 랜드마크 데이터를 시스템에 통합하고, 초당 프레임(FPS) 처리에 최적화된 **메인 이벤트 루프 및 스트리밍 구조 구축**
- **비동기 성능 최적화**: `QTimer` 기반의 비동기 프레임 처리 방식을 도입하여 **영상 분석 중 발생하는 UI 프리징 현상을 해결**하고 시스템의 실시간 응답성 확보
- **판단 알고리즘 시스템화**: EAR(Eye Aspect Ratio) 수치를 기반으로 **연속 프레임 카운팅 로직**을 구현하여 판별 신뢰도 향상
- **멀티미디어 피드백 제어**: `Pygame` 및 `PIL`을 활용하여 상황별 **음성 경고 재생 및 실시간 시각화 UI** 구현

**[트러블슈팅]**
- 고해상도 영상 처리 시 랜드마크 계산 부하로 인한 프레임 드랍 문제를 비동기 처리 및 연산 최적화를 통해 해결

<br/>

## 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
