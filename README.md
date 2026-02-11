<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="banner" />
</p>

# 🐶 안녕하세요. 방혁입니다. 

### 🔙 백엔드 개발자 
- Spring Boot를 주력으로 안정적이고 확장 가능한 API를 설계하고 구현합니다.
- JWT 기반 인증/인가, MySQL/JPA, Redis를 활용한 서비스 개발 및 운영 경험이 있습니다.
- 대규모 트래픽 처리를 위한 시스템 아키텍처에 관심이 많으며, Redis 분산 캐시 라우팅 알고리즘인 D-HASH를 개발해 성능 최적화를 연구하고 논문을 작성한 경험이 있습니다.
- 블로그: [hzeror.blog](https://bh1848.github.io/hzeror)
- 이메일: bh1848@naver.com

### 🥷 기술
<p>
  <img src="https://img.shields.io/badge/Java-111827?style=flat&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-111827?style=flat&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring%20Boot-111827?style=flat&logo=springboot&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring%20Security-111827?style=flat&logo=springsecurity&logoColor=white" />
  <img src="https://img.shields.io/badge/JPA%2FHibernate-111827?style=flat&logo=hibernate&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-111827?style=flat&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis-111827?style=flat&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS-111827?style=flat&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-111827?style=flat&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Nginx-111827?style=flat&logo=nginx&logoColor=white" />
</p>

<br/>

## 🔬 연구

### D-HASH: 분산 캐시 Hot-key 해결 알고리즘 개발 (SCIE)
<img src="https://img.shields.io/badge/SCIE-Accepted-0066CC?style=flat-square&logo=googlescholar&logoColor=white"/> <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>

> **Hot-key로 인한 서버 부하 불균형을 해결하는 동적 라우팅 기법**

- **문제 정의:** 특정 키 요청 증가(Hot-key) 시 발생하는 단일 노드 과부하 현상 해결
- **해결 방안:** 실시간 접근 빈도 감지 및 **동적 라우팅 알고리즘** 개발
- **연구 성과:** Consistent Hashing 대비 **부하 표준편차 33.8% 감소** 달성
- **담당 역할:** 알고리즘 개발, 실험 설계·구현·분석, 논문 작성 (제1저자)
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/D-HASH) | [📝 Paper (SCIE / TIIS 2026)](https://doi.org/10.3837/tiis.2026.xx.xxx)

<br/>

### MySQL vs Redis 성능 비교 벤치마크 (KCI)
<img src="https://img.shields.io/badge/KCI-Published-00C7B7?style=flat-square"/> <img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>

> **RDBMS(MySQL)와 NoSQL(Redis)의 실제 응답 속도 비교·분석**

- **연구 목표:** 데이터 연산 유형에 따른 DB별 성능 차이 검증
- **실험 결과:** Redis가 MySQL 대비 **평균 7.8배 빠름**을 입증 (1.39ms vs 0.17ms)
- **활용 방안:** 실제 시스템에서의 캐시 도입 기준 및 데이터 저장 전략 확립
- **담당 역할:** 실험 설계·구현·분석 (제1저자)
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/mysql-redis-benchmark) | [📜 Paper (KCI / JICS 2024)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)

<br/>

## 👨‍💻 프로젝트

### 동구라미 (2024.05 ~ 2025.03)
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>

> **대학교 중앙 동아리 및 소모임 통합 관리 플랫폼**

- **프로젝트 소개:** 교내 동아리 홍보, 가입 신청 간소화, 부원 관리 등 동아리 운영의 전 과정을 지원하는 서비스입니다.
- **주요 구현 및 성과:**
    - **QueryDSL 도입:** 동적 쿼리를 활용해 복잡한 필터링(카테고리/태그) 검색 API 구현
    - **Redis 캐싱:** 자주 조회되는 메인 페이지 동아리 목록에 캐싱을 적용해 조회 성능 개선
    - **CI/CD 구축:** Github Actions와 Docker를 활용하여 AWS EC2 자동 배포 환경 구성
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/USW-Circle-Link-Server)

<br/>

### 수챗 (2023.09 ~ 2024.10)
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/WebSocket-010101?style=flat-square&logo=socketdotio&logoColor=white"/>

> **대학교 이메일 인증 기반 랜덤 매칭 및 실시간 채팅 서비스**

- **프로젝트 소개:** 교내 이메일 인증을 통해 신뢰할 수 있는 익명 커뮤니티를 형성하고, 실시간 1:1 랜덤 매칭을 제공합니다.
- **주요 구현 및 성과:**
    - **WebSocket 채팅:** Stomp 프로토콜을 활용하여 실시간 양방향 1:1 채팅 기능 구현
    - **Redis Pub/Sub:** 다중 서버 확장을 고려하여 메시지 브로커 구조 설계 및 세션 관리
    - **인증 시스템:** 학교 이메일 인증 로직 및 JWT 기반의 사용자 인가 처리 담당
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/suchat-backend)

<br/>

### 요분정 (2024.09 ~ 2024.11)
<img src="https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white"/>

> **딥러닝 객체 인식을 활용한 쓰레기 자동 분류 및 리워드 앱**

- **프로젝트 소개:** 사용자가 쓰레기를 촬영하면 AI가 종류를 분류하고, 올바른 분리수거 시 포인트를 지급합니다.
- **주요 구현 및 성과:**
    - **AI Model Serving:** PyTorch 모델을 Flask 서버에 탑재하여 이미지 추론 REST API 개발
    - **ONNX 최적화:** YOLOv5 모델을 ONNX로 변환/경량화하여 서버 응답 속도 개선
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/yobunjung-backend)

<br/>

### 졸음운전 방지 시스템 (2023.09 ~ 2023.11)
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white"/>

> **Computer Vision 기반 실시간 운전자 눈 깜빡임 감지 솔루션**

- **프로젝트 소개:** 웹캠을 통해 운전자의 눈 깜빡임을 실시간으로 분석하여 졸음운전을 경고합니다.
- **주요 구현 및 성과:**
    - **알고리즘 구현:** Dlib 68 Face Landmark를 이용해 눈의 개폐 정도(EAR) 계산 로직 구현
    - **영상 처리:** OpenCV를 활용한 실시간 영상 프레임 전처리 및 경고음 출력 로직 개발
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/drowsy-driving-prevention)

<br/>

## 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
