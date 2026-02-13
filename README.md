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

### [🪜 D-HASH: Dynamic Hot-key Aware Scalable Hashing (SCIE)](https://github.com/bh1848/D-HASH)
> **개요:** 대규모 트래픽 환경에서 특정 키(Hot-key)에 요청이 집중될 때 발생하는 단일 노드 과부하 문제 해결을 위한 알고리즘 개발
> **스택:** Python, Redis, Docker  
> **역할:** 제1저자 (알고리즘 설계, 실험 설계·구현·분석, 논문 작성)  
> **성과:** 독자적인 동적 라우팅 알고리즘을 개발하여 Consistent Hashing 대비 **부하 표준편차 33.8% 감소** 달성  
> **논문:** [📝 Paper (SCIE / TIIS 2026)](https://doi.org/10.3837/tiis.2026.xx.xxx)

**1. 동적 라우팅 알고리즘 설계 (Window-Based Routing)**
- **문제:** 단순히 요청을 분산하면 캐시 미스가 발생하거나 데이터 정합성이 깨짐.
- **해결:**
    - **승격(Promotion) 로직:** LRU 카운터를 통해 요청 빈도가 임계값(T)을 넘는 키를 실시간 감지하여 Hot-key로 승격.
    - **Guard Phase 도입:** 승격 직후 바로 트래픽을 분산하지 않고, 일정 윈도우(W) 동안은 데이터를 복제(Pre-warming)하는 **Guard Phase**를 두어 초기 캐시 미스를 방지했습니다.
    - **결정론적 라우팅:** 랜덤 방식 대신 요청 횟수 기반의 윈도우 스위칭 기법을 적용하여, 메인 노드와 대체 노드 간의 부하를 결정론적으로 분배했습니다.

**2. 데이터 정합성 및 성능 최적화**
- **Write-Primary 정책:** 읽기 요청은 분산하되, 쓰기/수정 요청은 항상 **Primary Node**로만 향하게 하여 분산 환경에서의 데이터 파편화를 방지했습니다.
- **Python 최적화:** `xxHash` 라이브러리를 적용하여 해싱 속도를 높이고, 클래스에 `__slots__`를 선언하여 대량의 키 객체 생성 시 **메모리 사용량을 최적화**했습니다.

**3. 정량적 성과**
- NASA 웹 로그 및 Zipfian 분포 데이터셋 실험 결과, 기존 Consistent Hashing 대비 **서버 간 부하 표준편차(Load Std Dev) 33.8% 감소**를 달성하여 시스템 안정성을 입증했습니다.

<br/>

### [⚖️ MySQL vs Redis 성능 비교 벤치마크 (KCI)](https://github.com/bh1848/mysql-redis-benchmark)
> **개요:** 단순한 기술 도입이 아닌, 데이터의 성격과 연산 유형에 따른 최적의 저장소를 선정하기 위한 정량적 비교 분석 연구  
> **스택:** Java, Spring Boot, MySQL, Redis  
> **성과:** 대량 데이터 처리 시 Redis가 MySQL 대비 **평균 7.8배(1.39ms vs 0.17ms) 빠름**을 실험적으로 입증  
> **역할:** 제1저자 (실험 설계·구현·분석)  
> **논문:** [📜 Paper (KCI / JICS 2024)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)

**1. 객체 지향적 벤치마크 프레임워크 설계**
- **템플릿 메서드 패턴 적용:** 공정한 비교를 위해 `AbstractBatchExperiment` 추상 클래스를 정의하여 측정 로직(타이머, 반복 횟수 등)을 통일하고, DB별 구현체(`MysqlBatchExperiment`, `RedisBatchExperiment`)가 실제 연산만 수행하도록 설계했습니다.
- **대량 데이터 배치 처리:** 단건 처리가 아닌 **Batch Processing** 성능을 검증하기 위해 대용량 데이터의 일괄 삽입(Insert), 조회(Select), 수정(Update), 삭제(Delete) 시나리오를 구현했습니다.

**2. 정량적 데이터 분석 및 성과**
- **성능 격차 규명:** 실험 결과, 단순 Key-Value 조회 시 Redis가 MySQL(Disk I/O 기반) 대비 **평균 7.8배(1.39ms vs 0.17ms) 빠른 응답 속도**를 보임을 입증했습니다.
- **아키텍처 제언:** 쓰기(Write) 연산이 빈번한 환경과 읽기(Read) 위주의 환경에서의 성능 변화 추이를 분석하여, **데이터의 정합성이 중요한 원장 데이터는 MySQL에, 빈번한 조회 데이터는 Redis에 위임**하는 하이브리드 아키텍처의 수치적 근거를 마련했습니다.

<br/>

##  💻 Projects

### [🌕 동구라미: 대학교 동아리 통합 관리 플랫폼](https://github.com/bh1848/USW-Circle-Link-Server)
> **개요:** 교내 동아리 행정 업무 자동화 및 학생들의 활동 접근성을 높이는 웹어플리케이션 서비스 (2024.05 ~ 2025.03)  
> **스택:** Java, Spring Boot, Spring Security, JPA/QueryDSL, MySQL, Redis, AWS   
> **역할:** Backend  

**1. 보안 및 인증/인가 시스템 구축**
- **JWT + Redis 인증:** Access Token과 Refresh Token을 활용한 이중 토큰 방식을 구현하고, Redis를 통해 **Refresh Token Rotation**을 적용하여 탈취 시 보안 위협을 최소화했습니다.
- **보안 쿠키 전략:** XSS 및 CSRF 공격 방지를 위해 Refresh Token을 `HttpOnly`, `Secure`, `SameSite=Lax` 속성이 적용된 쿠키로 관리했습니다.
- **Spring Security 커스텀:** `UserDetailsService`를 재정의하여 관리자, 동아리 회장, 일반 학생의 권한을 분리하고 도메인별 접근 제어를 구현했습니다.

**2. 데이터 처리 및 성능 최적화**
- **QueryDSL 도입:** 동아리 검색 및 필터링(문자열 필터) 기능을 위해 동적 쿼리를 작성하고, 복잡한 조회 로직을 Type-Safe하게 구현했습니다.
- **JPQL 최적화:** `new` 오퍼레이션을 활용한 DTO Projection으로 불필요한 데이터 조회를 줄이고, 연관 데이터 삭제 시 **Bulk Delete** 쿼리를 사용하여 N+1 문제를 해결했습니다.
~~~java
// Bulk Delete 예시: N번의 Delete 쿼리 대신 한 번의 쿼리로 처리
em.createQuery("DELETE FROM ClubMemberAccountStatus cmas WHERE cmas.club.clubId = :clubId")
   .setParameter("clubId", clubId)
   .executeUpdate();
~~~
- **DB 운영:** AWS RDS(MySQL)와 Redis를 연동하여 영속성 데이터와 캐시/세션 데이터를 분리 운영했습니다.

**3. 인프라 및 파일 시스템**
- **AWS S3 Presigned URL:** 서버의 부하를 줄이기 위해 클라이언트가 S3로 직접 파일을 업로드하는 Presigned URL 방식을 도입하여 I/O Blocking을 방지했습니다.
- **파일 검증 로직:** 단순 확장자 체크뿐만 아니라 파일 시그니처(Magic Number)를 검증하여 위변조된 파일 업로드를 차단했습니다.
- **환경 분리:** `application-dev.yml`, `application-prod.yml` 등 프로파일을 분리하여 민감 정보를 관리하고 배포 환경을 최적화했습니다.

**4. API 품질 및 안정성**
- **Global Exception Handling:** `@RestControllerAdvice`를 활용해 예외를 중앙에서 처리하고, 표준화된 `ErrorResponse` 포맷을 정의하여 프론트엔드와의 협업 효율을 높였습니다.
- **스마트 로깅:** 운영(Prod) 환경에서는 클라이언트 실수인 4xx 에러 로그를 남기지 않도록 설정하여 **로그 가시성**을 확보하고 디스크 낭비를 막았습니다.
- **데이터 검증:** `@Valid` 및 커스텀 어노테이션을 활용해 요청 데이터의 유효성 검사(Validation)를 꼼꼼하게 처리했습니다.

**5. 비즈니스 로직 구현**
- **기능 구현:** 앱 관리자 기능, 중앙동아리 연합회 관리, 공지사항 CRUD, 동아리 지원서 제출, 동아리 목록 조회 로직 전반을 개발했습니다.

<br/>

### [💬 수챗: 익명 랜덤 매칭 서비스](https://github.com/bh1848/suchat-backend)
> **개요:** 교내 이메일 인증을 통해 신뢰할 수 있는 익명 커뮤니티 및 실시간 1:1 랜덤 매칭 플랫폼 (2023.09 ~ 2024.10)  
> **스택:** Java, Spring Boot, Redis(ZSet), WebSocket, Async, MySQL  
> **역할:** Backend

**1. 실시간 랜덤 매칭 알고리즘**
- **Redis ZSet 대기열:** 매칭 대기열을 DB가 아닌 Redis Sorted Set(ZSet)으로 구현하여, 입/퇴장 빈도가 잦은 매칭 요청의 I/O 성능을 확보하고 대기 순서를 보장했습니다.
- **비동기 매칭 처리:** `CompletableFuture`와 `@Async`를 활용해 매칭 로직을 비동기로 처리하여, 사용자가 대기하는 동안 서버 스레드가 차단(Blocking)되지 않도록 최적화했습니다.
- **매칭 로직:** 대기열에 2명 이상이 모이면 즉시 UUID 기반의 고유 채팅방(Room ID)을 생성하고 양쪽 사용자에게 배정하는 로직을 구현했습니다.

**2. 폐쇄형 인증 및 보안 시스템**
- **이메일 인증(학교 도메인):** `JavaMailSender`를 활용해 학교 웹메일(@suwon.ac.kr)로 인증 링크를 발송하고, 토큰 검증을 통과해야만 정회원으로 전환되도록 하여 외부인의 접근을 원천 차단했습니다.
- **임시 회원 분리 설계:** 회원가입 시 바로 `Member` 테이블에 넣지 않고 `MemberTemp`(임시) 테이블에 우선 저장한 뒤, 인증이 완료된 시점에 이관하는 구조로 설계하여 **더미 데이터 생성을 방지**했습니다.
- **JWT + Redis 보안:** Access Token과 Refresh Token을 발급하며, Refresh Token은 **Redis(TTL 설정)**에 저장하여 로그아웃 시 토큰을 즉시 무효화하거나 탈취 위험을 관리할 수 있도록 구현했습니다.

**3. 회원 관리 로직**
- **서비스 계층 분리:** 인증 전 접근 가능한 `MemberOpenService`(가입, 로그인)와 인증 후 접근 가능한 `MemberSecureService`로 비즈니스 로직을 분리하여 보안성을 강화했습니다.

<br/>

### [♻️ 요분정: AI 기반 쓰레기 분류 및 리워드 앱](https://github.com/bh1848/yobunjung-backend)
> **개요:** 딥러닝 객체 인식으로 쓰레기를 분류하고 IoT 수거함과 연동하여 리워드를 지급하는 자원 순환 서비스 (2024.09 ~ 2024.11)  
> **스택:** Python, Flask, MySQL, ONNX, AWS, OpenCV  
> **역할:** Backend & AI Serving

**1. AI 모델 경량화 및 실시간 서빙**
- **ONNX 런타임 적용:** 학습된 YOLO 모델을 실제 서버 환경에서 빠르고 가볍게 구동하기 위해 **ONNX 포맷으로 변환**하여 경량화된 추론 환경을 구축했습니다.
- **이미지 전처리 최적화:** OpenCV를 활용해 수거함 카메라(아두이노)에서 전송된 이미지의 크기 조정(Resize), 정규화(Normalization), 채널 변환(HWC→CHW) 로직을 직접 구현하여 모델 인식률을 최적화했습니다.

**2. 하드웨어-서버-클라이언트 데이터 파이프라인**
- **SSE(Server-Sent Events) 통신:** 아두이노가 쓰레기를 감지하고 분류 결과를 서버로 보내면, 사용자 앱(Client)에 실시간으로 포인트 적립 알림을 띄우기 위해 **SSE 프로토콜**을 구현했습니다.
- **동시성 제어:** 하드웨어와 앱 간의 비동기 통신 중 데이터 정합성을 보장하기 위해 `threading.Event`와 `Lock`을 활용하여 안정적인 이벤트 스트리밍 구조를 설계했습니다.
- **아두이노 연동 협업:** 하드웨어 팀원과 협업하여 HTTP 통신 규격을 정의하고, 이미지 전송 및 결과 반환 프로토콜을 연동했습니다.

**3. 백엔드 아키텍처 및 인프라**
- **API 서버 구축:** Flask의 **Blueprint** 기능을 활용해 인증(Auth), 사용자(User), 재활용(Recycle) 등 기능별로 모듈화된 확장 가능한 백엔드 구조를 설계했습니다.
- **AWS 인프라 총괄:** AWS EC2 서버 배포 및 MySQL 데이터베이스 설계/구축을 전담하여 서비스의 운영 환경을 책임졌습니다.
- **부가 기능 구현:** 사용자 고유 ID와 분류 정보를 포함한 **QR 코드 생성(로고 오버레이)** 로직 및 JWT 인증 시스템을 개발했습니다.

<br/>

### [😴 딴짓 하지 말아줘: 졸음 운전 방지 솔루션](https://github.com/bh1848/drowsy-driving-prevention)
> **개요:** Computer Vision 기반으로 운전자의 졸음, 하품, 전방 미주시 상태를 실시간 감지하는 윈도우 애플리케이션 (2023.09 ~ 2023.11)   
> **스택:** Python, PyQt5, OpenCV, dlib    
> **역할:** Application Dev & CV Logic  

**1. 데스크탑 애플리케이션 UI/UX 개발**
- **PyQt5 기반 UI 구축:** `QMainWindow`를 상속받아 운전자 모니터링 화면, 상태 표시바, 제어 버튼이 포함된 직관적인 대시보드를 설계하고 구현했습니다.
- **실시간 영상 처리 파이프라인:** `QTimer`와 `OpenCV`를 연동하여 UI 끊김(Freezing) 없이 웹캠 영상을 프레임 단위로 캡처하고 분석 결과를 오버레이(Overlay)하는 비동기 처리 구조를 구현했습니다.

**2. 운전자 상태 판단 로직 구현**
- **졸음 감지 알고리즘(EAR):** `dlib`의 68개 얼굴 랜드마크를 활용, 눈의 종횡비를 계산하는 **EAR(Eye Aspect Ratio)** 공식을 코드로 구현하여 눈 감김 지속 시간을 기반으로 졸음 여부를 판단했습니다.
- **전방 미주시 및 하품 감지:** 얼굴의 각도와 입의 개폐 정도(MAR)를 수치화하여, 운전자가 정면을 보지 않거나 하품을 하는 상황을 실시간으로 탐지하는 로직을 작성했습니다.

**3. 시스템 통합 및 알림 시스템**
- **상태 기반 경고 시스템:** 정상, 졸음, 하품, 미주시 등 운전자의 상태를 4단계로 정의하고, `pygame` 라이브러리를 활용해 각 상황에 맞는 경고 음성(MP3)이 즉시 재생되도록 이벤트 핸들링을 구현했습니다.

<br/>

## 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
