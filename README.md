<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="banner" />
</p>

# 🐶 안녕하세요. 백엔드 개발자 방혁입니다. 

> **"단순한 구현 이상으로, 데이터에 기반해 성능을 개선하는 것과 안정적인 아키텍처를 지향합니다."**

사용자 경험을 최우선으로 생각하며, 특히 **대용량 트래픽 처리**와 **시스템 아키텍처**에 깊은 관심을 가지고 있습니다. 
- **Email:** bh1848@naver.com
- **Blog:** [hzeror.blog](https://bh1848.github.io/hzeror)

### 🥷 기술
**Main (Product-Level)**
<p>
  <img src="https://img.shields.io/badge/Java-111827?style=flat&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring%20Boot-111827?style=flat&logo=springboot&logoColor=white" />
  <img src="https://img.shields.io/badge/JPA%2FHibernate-111827?style=flat&logo=hibernate&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-111827?style=flat&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis-111827?style=flat&logo=redis&logoColor=white" />
</p>

**Sub & Tools (Experience)**
<p>
  <img src="https://img.shields.io/badge/Python-111827?style=flat&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring%20Security-111827?style=flat&logo=springsecurity&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS-111827?style=flat&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-111827?style=flat&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Nginx-111827?style=flat&logo=nginx&logoColor=white" />
</p>

<br/>

## 🔬 연구

### 1. D-HASH: 분산 캐시 Hot-key 해결 알고리즘 개발 (SCIE)
<img src="https://img.shields.io/badge/SCIE-Accepted-0066CC?style=flat-square&logo=googlescholar&logoColor=white"/> <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/Algorithm-Optimization-orange?style=flat-square"/>

> **Hot-key 병목 현상을 해결하는 클라이언트 사이드 동적 라우팅 프로토콜**
> *KSII TIIS 2026 게재 (제1저자)*

<br/>

**연구 배경**
Consistent Hashing 환경에서 특정 데이터(Hot-key)에 트래픽이 쏠릴 경우(상위 1% 키가 요청의 40% 점유), 단일 노드 과부하로 인해 전체 시스템 성능이 저하되는 문제를 발견했습니다. 이를 별도의 프록시 서버 없이 클라이언트단에서 해결하고자 했습니다.

<br/>

**핵심 성과 및 기술적 도전**

**1. 동적 라우팅 알고리즘 설계 (Window-Based Routing)**
- **문제:** 단순히 요청을 분산하면 캐시 미스(Cache Miss)가 발생하거나 데이터 정합성이 깨짐.
- **해결:**
    - **승격(Promotion) 로직:** LRU 카운터를 통해 요청 빈도가 임계값($T$)을 넘는 키를 실시간 감지하여 Hot-key로 승격.
    - **Guard Phase 도입:** 승격 직후 바로 트래픽을 분산하지 않고, 일정 윈도우($W$) 동안은 데이터를 복제(Pre-warming)하는 **'보호 구간(Guard Phase)'**을 두어 초기 캐시 미스를 방지했습니다.
    - **결정론적 라우팅:** 랜덤 방식 대신 요청 횟수 기반의 윈도우 스위칭 기법을 적용하여, 메인 노드와 대체 노드 간의 부하를 **결정론적(Deterministic)**으로 분배했습니다.

**2. 데이터 정합성 및 성능 최적화**
- **Write-Primary 정책:** 읽기 요청은 분산하되, 쓰기/수정 요청은 항상 **메인 노드(Primary Node)**로만 향하게 하여 분산 환경에서의 데이터 파편화를 방지했습니다.
- **Python 최적화:** `xxHash` 라이브러리를 적용하여 해싱 속도를 높이고, 클래스에 `__slots__`를 선언하여 대량의 키 객체 생성 시 **메모리 사용량을 최적화**했습니다.

**3. 정량적 성과 (Experimental Results)**
- NASA 웹 로그 및 Zipfian 분포 데이터셋 실험 결과, 기존 Consistent Hashing 대비 **서버 간 부하 표준편차(Load Std Dev) 33.8% 감소**를 달성하여 시스템 안정성을 입증했습니다.

<br/>

- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/D-HASH) | [📝 Paper (SCIE / TIIS 2026)](https://doi.org/10.3837/tiis.2026.xx.xxx)

<br/>


### 2. MySQL vs Redis 성능 비교 벤치마크 (KCI)
<img src="https://img.shields.io/badge/KCI-Published-00C7B7?style=flat-square"/> <img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/Strategy-Pattern-orange?style=flat-square"/>

> **데이터 연산 유형에 따른 RDBMS vs NoSQL 성능 차이 검증 및 캐시 도입 전략 수립**
> *한국정보통신학회논문지(JICS) 2024 게재 (제1저자)*

<br/>

**연구 배경**
단순히 "Redis가 빠르다"는 통념을 넘어, **어떤 연산(CRUD)에서 얼마나(How much) 빠른지**를 정량적으로 분석하여, 실제 서비스 아키텍처 설계 시 **캐시 도입의 명확한 기준(Trade-off)**을 제시하고자 했습니다.

<br/>

**핵심 구현 및 실험 설계**

**1. 객체 지향적 벤치마크 프레임워크 설계 (Testbed Architecture)**
- **템플릿 메서드 패턴 적용:** 공정한 비교를 위해 `AbstractBatchExperiment` 추상 클래스를 정의하여 측정 로직(타이머, 반복 횟수 등)을 통일하고, DB별 구현체(`MysqlBatchExperiment`, `RedisBatchExperiment`)가 실제 연산만 수행하도록 설계했습니다.
- **대량 데이터 배치 처리:** 단건 처리가 아닌 **Batch Processing** 성능을 검증하기 위해 대용량 데이터의 일괄 삽입(Insert), 조회(Select), 수정(Update), 삭제(Delete) 시나리오를 구현했습니다.

**2. 정량적 데이터 분석 및 성과**
- **성능 격차 규명:** 실험 결과, 단순 Key-Value 조회 시 Redis가 MySQL(Disk I/O 기반) 대비 **평균 7.8배(1.39ms vs 0.17ms) 빠른 응답 속도**를 보임을 입증했습니다.
- **아키텍처 제언:** 쓰기(Write) 연산이 빈번한 환경과 읽기(Read) 위주의 환경에서의 성능 변화 추이를 분석하여, **"데이터의 정합성이 중요한 원장 데이터는 MySQL에, 빈번한 조회 데이터는 Redis에 위임"**하는 하이브리드 아키텍처의 수치적 근거를 마련했습니다.

<br/>

- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/mysql-redis-benchmark) | [📜 Paper (KCI / JICS 2024)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)

<br/>

## 👨‍💻 프로젝트

### 🌕 동구라미
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>

> **대학교 중앙 동아리 및 소모임 통합 관리 플랫폼**
> *2024.05 ~ 2025.03 (팀 프로젝트)*

<br/>

**프로젝트 소개**
교내 동아리 홍보, 가입 신청 간소화, 부원 관리 등 동아리 운영의 전 과정을 지원하는 서비스입니다. 기존에 파편화되어 있던 동아리 정보를 통합하고, 수기 관리의 비효율을 해결하기 위해 개발했습니다.

<br/>

**담당 업무 (Backend)**

**1. 보안 및 인증/인가 시스템 구축 (Security & Auth)**
- **JWT + Redis 인증:** Access Token과 Refresh Token을 활용한 이중 토큰 방식을 구현하고, Redis를 통해 **Refresh Token Rotation**을 적용하여 탈취 시 보안 위협을 최소화했습니다.
- **보안 쿠키 전략:** XSS 및 CSRF 공격 방지를 위해 Refresh Token을 `HttpOnly`, `Secure`, `SameSite=Lax` 속성이 적용된 쿠키로 관리했습니다.
- **Spring Security 커스텀:** `UserDetailsService`를 재정의하여 관리자, 동아리 회장, 일반 학생의 권한을 분리하고 도메인별 접근 제어를 구현했습니다.

**2. 데이터 처리 및 성능 최적화 (Database & Performance)**
- **QueryDSL 도입:** 동아리 검색 및 필터링(문자열 필터) 기능을 위해 동적 쿼리를 작성하고, 복잡한 조회 로직을 Type-Safe하게 구현했습니다.
- **JPQL 최적화:** `new` 오퍼레이션을 활용한 DTO Projection으로 불필요한 데이터 조회를 줄이고, 연관 데이터 삭제 시 **Bulk Delete** 쿼리를 사용하여 N+1 문제를 해결했습니다.
~~~java
// Bulk Delete 예시: N번의 Delete 쿼리 대신 한 번의 쿼리로 처리
em.createQuery("DELETE FROM ClubMemberAccountStatus cmas WHERE cmas.club.clubId = :clubId")
   .setParameter("clubId", clubId)
   .executeUpdate();
~~~
- **DB 운영:** AWS RDS(MySQL)와 Redis를 연동하여 영속성 데이터와 캐시/세션 데이터를 분리 운영했습니다.

**3. 인프라 및 파일 시스템 (DevOps & Infrastructure)**
- **AWS S3 Presigned URL:** 서버의 부하를 줄이기 위해 클라이언트가 S3로 직접 파일을 업로드하는 Presigned URL 방식을 도입하여 I/O Blocking을 방지했습니다.
- **파일 검증 로직:** 단순 확장자 체크뿐만 아니라 파일 시그니처(Magic Number)를 검증하여 위변조된 파일 업로드를 차단했습니다.
- **환경 분리:** `application-dev.yml`, `application-prod.yml` 등 프로파일을 분리하여 민감 정보를 관리하고 배포 환경을 최적화했습니다.

**4. API 품질 및 안정성 (Quality & Stability)**
- **Global Exception Handling:** `@RestControllerAdvice`를 활용해 예외를 중앙에서 처리하고, 표준화된 `ErrorResponse` 포맷을 정의하여 프론트엔드와의 협업 효율을 높였습니다.
- **스마트 로깅:** 운영(Prod) 환경에서는 클라이언트 실수인 4xx 에러 로그를 남기지 않도록 설정하여 **로그 가시성**을 확보하고 디스크 낭비를 막았습니다.
- **데이터 검증:** `@Valid` 및 커스텀 어노테이션을 활용해 요청 데이터의 유효성 검사(Validation)를 꼼꼼하게 처리했습니다.

**5. 핵심 비즈니스 로직 구현 (Business Logic)**
- **기능 구현:** 앱 관리자 기능, 중앙동아리 연합회 관리, 공지사항 CRUD, 동아리 지원서 제출, 동아리 목록 조회 로직 전반을 개발했습니다.

<br/>

- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/USW-Circle-Link-Server)

<br/>


### 💬 수챗
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/Java%20Mail-EA4335?style=flat-square&logo=gmail&logoColor=white"/>

> **대학교 이메일 인증 기반 익명 랜덤 매칭 서비스**
> *2023.09 ~ 2024.10 (팀 프로젝트)*

<br/>

**프로젝트 소개**
교내 이메일 인증을 통해 신뢰할 수 있는 익명 커뮤니티를 형성하고, 실시간 1:1 랜덤 매칭을 제공합니다. 기존 에브리타임 등 커뮤니티의 익명성을 보장하되, "우리 학교 학생"이라는 신뢰를 기반으로 안전한 소통 공간을 만들고자 했습니다.

<br/>

**담당 업무 (Backend)**

**1. 실시간 랜덤 매칭 알고리즘 (Matching System)**
- **Redis ZSet 대기열:** 매칭 대기열을 DB가 아닌 **Redis Sorted Set(ZSet)**으로 구현하여, 입/퇴장 빈도가 잦은 매칭 요청의 I/O 성능을 확보하고 대기 순서를 보장했습니다.
- **비동기 매칭 처리:** `CompletableFuture`와 `@Async`를 활용해 매칭 로직을 비동기로 처리하여, 사용자가 대기하는 동안 서버 스레드가 차단(Blocking)되지 않도록 최적화했습니다.
- **매칭 로직:** 대기열에 2명 이상이 모이면 즉시 UUID 기반의 고유 채팅방(Room ID)을 생성하고 양쪽 사용자에게 배정하는 로직을 구현했습니다.

**2. 폐쇄형 인증 및 보안 시스템 (Auth & Security)**
- **이메일 인증(학교 도메인):** `JavaMailSender`를 활용해 학교 웹메일(@suwon.ac.kr)로 인증 링크를 발송하고, 토큰 검증을 통과해야만 정회원으로 전환되도록 하여 외부인의 접근을 원천 차단했습니다.
- **임시 회원 분리 설계:** 회원가입 시 바로 `Member` 테이블에 넣지 않고 `MemberTemp`(임시) 테이블에 우선 저장한 뒤, 인증이 완료된 시점에 이관하는 구조로 설계하여 **더미 데이터 생성을 방지**했습니다.
- **JWT + Redis 보안:** Access Token과 Refresh Token을 발급하며, Refresh Token은 **Redis(TTL 설정)**에 저장하여 로그아웃 시 토큰을 즉시 무효화하거나 탈취 위험을 관리할 수 있도록 구현했습니다.

**3. 회원 관리 로직 (User Management)**
- **서비스 계층 분리:** 인증 전 접근 가능한 `MemberOpenService`(가입, 로그인)와 인증 후 접근 가능한 `MemberSecureService`로 비즈니스 로직을 분리하여 보안성을 강화했습니다.

<br/>

- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/suchat-backend)

<br/>

### ♻️ 요분정
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white"/> <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>

> **딥러닝 객체 인식을 활용한 쓰레기 자동 분류 및 리워드 앱**
> *2024.09 ~ 2024.11 (4인 프로젝트)*

<br/>

**프로젝트 소개**
사용자가 쓰레기를 촬영하면 AI가 종류(캔, 플라스틱, 종이)를 분류하여 **QR 코드를 발급**하고, 이를 수거함에 스캔하면 자동으로 문이 열려 투입 후 포인트를 지급하는 **IoT 기반 자원 순환 서비스**입니다.

<br/>

**담당 업무 (Backend & AI Serving)**

**1. AI 모델 경량화 및 실시간 서빙 (AI Inference)**
- **ONNX 런타임 적용:** 학습된 YOLO 모델을 실제 서버 환경에서 빠르고 가볍게 구동하기 위해 **ONNX 포맷으로 변환**하여 경량화된 추론 환경을 구축했습니다.
- **이미지 전처리 최적화:** OpenCV를 활용해 수거함 카메라(아두이노)에서 전송된 이미지의 크기 조정(Resize), 정규화(Normalization), 채널 변환(HWC→CHW) 로직을 직접 구현하여 모델 인식률을 최적화했습니다.

**2. 하드웨어-서버-클라이언트 데이터 파이프라인 (IoT Integration)**
- **SSE(Server-Sent Events) 통신:** 아두이노가 쓰레기를 감지하고 분류 결과를 서버로 보내면, 사용자 앱(Client)에 실시간으로 포인트 적립 알림을 띄우기 위해 **SSE 프로토콜**을 구현했습니다.
- **동시성 제어:** 하드웨어와 앱 간의 비동기 통신 중 데이터 정합성을 보장하기 위해 `threading.Event`와 `Lock`을 활용하여 안정적인 이벤트 스트리밍 구조를 설계했습니다.
- **아두이노 연동 협업:** 하드웨어 팀원과 협업하여 HTTP 통신 규격을 정의하고, 이미지 전송 및 결과 반환 프로토콜을 연동했습니다.

**3. 백엔드 아키텍처 및 인프라 (Architecture & Infra)**
- **API 서버 구축:** Flask의 **Blueprint** 기능을 활용해 인증(Auth), 사용자(User), 재활용(Recycle) 등 기능별로 모듈화된 확장 가능한 백엔드 구조를 설계했습니다.
- **AWS 인프라 총괄:** AWS EC2 서버 배포 및 MySQL 데이터베이스 설계/구축을 전담하여 서비스의 운영 환경을 책임졌습니다.
- **부가 기능 구현:** 사용자 고유 ID와 분류 정보를 포함한 **QR 코드 생성(로고 오버레이)** 로직 및 JWT 인증 시스템을 개발했습니다.

<br/>

- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/yobunjung-backend)

<br/>

### 😴 딴짓 하지 말아줘
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/PyQt5-41CD52?style=flat-square&logo=qt&logoColor=white"/> <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white"/> <img src="https://img.shields.io/badge/dlib-008000?style=flat-square"/>

> **Computer Vision 기반 실시간 운전자 졸음 및 전방 미주시 감지 솔루션**
> *2023.09 ~ 2023.11 (4인 프로젝트)*

<br/>

**프로젝트 소개**
웹캠을 통해 운전자의 얼굴을 실시간으로 분석하여 졸음(눈 감음), 하품, 전방 미주시 상태를 감지하고, 위험 단계에 따라 경고음과 시각적 알림을 제공하는 윈도우 애플리케이션입니다.

<br/>

**담당 업무 (Application Dev & CV Implementation)**

**1. 데스크탑 애플리케이션 UI/UX 개발 (GUI Development)**
- **PyQt5 기반 UI 구축:** `QMainWindow`를 상속받아 운전자 모니터링 화면, 상태 표시바, 제어 버튼이 포함된 직관적인 대시보드를 설계하고 구현했습니다.
- **실시간 영상 처리 파이프라인:** `QTimer`와 `OpenCV`를 연동하여 UI 끊김(Freezing) 없이 웹캠 영상을 프레임 단위로 캡처하고 분석 결과를 오버레이(Overlay)하는 비동기 처리 구조를 구현했습니다.

**2. 운전자 상태 판단 로직 구현 (Detection Logic)**
- **졸음 감지 알고리즘(EAR):** `dlib`의 68개 얼굴 랜드마크를 활용, 눈의 종횡비를 계산하는 **EAR(Eye Aspect Ratio)** 공식을 코드로 구현하여 눈 감김 지속 시간을 기반으로 졸음 여부를 판단했습니다.
- **전방 미주시 및 하품 감지:** 얼굴의 각도와 입의 개폐 정도(MAR)를 수치화하여, 운전자가 정면을 보지 않거나 하품을 하는 상황을 실시간으로 탐지하는 로직을 작성했습니다.

**3. 시스템 통합 및 알림 시스템 (System Integration)**
- **상태 기반 경고 시스템:** 정상, 졸음, 하품, 미주시 등 운전자의 상태를 4단계로 정의하고, `pygame` 라이브러리를 활용해 각 상황에 맞는 경고 음성(MP3)이 즉시 재생되도록 이벤트 핸들링을 구현했습니다.

<br/>

- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/drowsy-driving-prevention)

<br/>

## 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
