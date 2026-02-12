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
<img src="https://img.shields.io/badge/SCIE-Accepted-0066CC?style=flat-square&logo=googlescholar&logoColor=white"/> <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>

> **Hot-key로 인한 서버 부하 불균형을 해결하는 동적 라우팅 기법**

- **배경:** 대규모 트래픽 환경에서 특정 키(Hot-key)에 요청이 집중될 때 발생하는 단일 노드 과부하 문제 해결 필요
- **성과:** 독자적인 동적 라우팅 알고리즘을 개발하여 Consistent Hashing 대비 **부하 표준편차 33.8% 감소** 달성
- **역할:** 제1저자 (알고리즘 설계, Python 시뮬레이션 구현, 논문 작성)
- **링크:** [🐙 GitHub Repository](https://github.com/bh1848/D-HASH) | [📝 Paper (SCIE / TIIS 2026)](https://doi.org/10.3837/tiis.2026.xx.xxx)

### 2. MySQL vs Redis 성능 비교 벤치마크 (KCI)
<img src="https://img.shields.io/badge/KCI-Published-00C7B7?style=flat-square"/> <img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>

> **데이터 연산 유형에 따른 DB별 성능 차이 검증 및 캐시 전략 수립**

- **성과:** 대량 데이터 처리 시 Redis가 MySQL 대비 **평균 7.8배(1.39ms vs 0.17ms) 빠름**을 실험적으로 입증
- **의의:** 단순 도입이 아닌, 수치적 근거에 기반한 캐싱 전략 수립 기준 마련
- **역할:** 실험 설계·구현·분석 (제1저자)
- **링크:** [🐙 GitHub Repository](https://github.com/bh1848/mysql-redis-benchmark) | [📜 Paper (KCI / JICS 2024)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)

<br/>

## 👨‍💻 프로젝트

### 동구라미 (2024.05 ~ 2025.03)
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white"/>

> **대학교 중앙 동아리 및 소모임 통합 관리 플랫폼**

- **프로젝트 소개:** 교내 동아리 홍보, 가입 신청 간소화, 부원 관리 등 동아리 운영의 전 과정을 지원하는 서비스입니다.
- **담당 업무:**
    - **QueryDSL 도입:** 
    - **JWT 담:** 
    - **어플 관리자, 중앙동아리 연합회, 공지사항, 동아리 지원서 기능 담당:**
    - **MySQL, Redis 데이터베이스 관리**
    - **AWS RDS 연동**
    - **사진 업로드 관련 담당 S3 활용**
    - **문자열 필터 담당**
    - **errorRespone 담당**
    - **globalExceprion 담당**
    - **yml 파일 설정 담당**
    - **validation 담당**
    - **jpa 에서 쿼리 날리는거 적용**
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/USW-Circle-Link-Server)

<br/>

### 수챗 (2023.09 ~ 2024.10)
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/WebSocket-010101?style=flat-square&logo=socketdotio&logoColor=white"/>

> **대학교 이메일 인증 기반 랜덤 매칭 및 실시간 채팅 서비스**

- **프로젝트 소개:** 교내 이메일 인증을 통해 신뢰할 수 있는 익명 커뮤니티를 형성하고, 실시간 1:1 랜덤 매칭을 제공합니다.
- **담당 업무:**
    - **회원가입/로그인/로그아웃/탈퇴 담당:**
    - **JWT 담당**
    - **Redis Pub/Sub:**
    - **인증 시스템:** 학교 이메일 인증 로직 및 JWT 기반의 사용자 인가 처리 담당
    - **매칭 알고리즘 담당**
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/suchat-backend)

<br/>

### 요분정 (2024.09 ~ 2024.11)
<img src="https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white"/> <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white"/>

> **딥러닝 객체 인식을 활용한 쓰레기 자동 분류 및 리워드 앱**

- **프로젝트 소개:** 사용자가 쓰레기를 촬영하면 AI가 종류를 분류하고, 올바른 분리수거 시 포인트를 지급합니다.
- **담당 업무:**
    - **백엔드 전체 코드 담당:**
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/yobunjung-backend)

<br/>

### 졸음운전 방지 시스템 (2023.09 ~ 2023.11)
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white"/>

> **Computer Vision 기반 실시간 운전자 눈 깜빡임 감지 솔루션**

- **프로젝트 소개:** 웹캠을 통해 운전자의 눈 깜빡임을 실시간으로 분석하여 졸음운전을 경고합니다.
- **담당 업무:**
    - **알고리즘 학습, 아두이노 제외 모든 코드 담당:** 
- **관련 링크:** [🐙 GitHub Repository](https://github.com/bh1848/drowsy-driving-prevention)

<br/>

## 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
