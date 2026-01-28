<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="banner" />
</p>

# 🐶 안녕하세요. 백엔드 개발자 방혁입니다.

### 🔙 Backend Developer
- **Spring Boot**를 주력으로 안정적이고 확장 가능한 API를 설계하고 구현합니다.
- JWT 기반 인증/인가, MySQL/JPA, Redis를 활용한 서비스 개발 및 운영 경험이 있습니다.
- 대규모 트래픽 처리에 관심이 많으며, **Redis 분산 캐시 라우팅(D-HASH) 연구**를 통해 성능 최적화를 검증한 경험이 있습니다.

### 📱 Contact me
- Email: bh1848@naver.com

<br/>

## 🥷 Skills
<p>
  <img src="https://img.shields.io/badge/Java-111827?style=flat&logo=openjdk&logoColor=white" />
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

## 🔬 Research & Engineering

<details>
  <summary>
    <b>D-HASH: 분산 캐시 핫키(Hot-key) 해결 알고리즘</b>
    <img src="https://img.shields.io/badge/SCIE-Accepted-0066CC?style=flat-square&logo=googlescholar&logoColor=white"/>
    <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
    <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>
  </summary>

<br>

**분산 캐시 환경의 트래픽 쏠림 현상을 해결하기 위한 동적 라우팅 기법 제안 및 구현**

- **Problem:** 특정 키에 요청이 집중될 때 발생하는 단일 노드 과부하 및 시스템 불안정성 해결
- **Solution:** 접근 빈도 기반의 실시간 핫키 감지 및 주/대체 노드 간 동적 윈도우 스위칭 알고리즘 설계
- **Impact:** 기존 Consistent Hashing 대비 **부하 표준편차 26.7% 감소** (Throughput 유지)
- **Role:** 알고리즘 설계·구현부터 벤치마크 환경 구축까지 **연구 개발 전 과정 주도** (제1저자)
- **Links:**
  - 🐙 [**GitHub Repository**](https://github.com/bh1848/D-HASH) (Official Implementation)
  - 📝 [**Paper (SCIE / TIIS 2026)**](https://doi.org/10.3837/tiis.2026.xx.xxx)

</details>

<details>
  <summary>
    <b>MySQL vs Redis 데이터 처리 성능 비교 분석</b>
    <img src="https://img.shields.io/badge/KCI-Published-00C7B7?style=flat-square"/>
    <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
    <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>
  </summary>

<br>

**RDBMS(MySQL)와 NoSQL(Redis)의 배치 처리 성능 비교를 통한 캐시 도입 기준 연구**

- **Problem:** 데이터 크기 및 연산 유형에 따른 디스크 DB와 인메모리 DB의 성능 교차점 및 효율성 분석
- **Action:** 시나리오별 Latency/Throughput 벤치마크 설계 및 실험 데이터 분석을 통한 정량적 지표 도출
- **Impact:** 실제 시스템 설계 시 **캐시 도입 유무를 판단할 수 있는 기술적 근거** 마련
- **Role:** 실험 설계 및 전체 기술 구현 총괄, 데이터 분석 (제1저자)
- **Links:**
  - 🐙 [**GitHub Repository**](https://github.com/bh1848/mysql-redis-benchmark) (Official Implementation)
  - 📜 [**Paper (KCI / JICS 2024)**](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)

</details>

<br/>

## 👨‍💻 Projects

<details>
  <summary><b>동구라미</b> · 2024.05 ~ 2025.03 · Backend</summary>

- 🐣 동아리 지원 · 홍보 · 관리 통합 플랫폼
- **Repo:** [USW-Circle-Link-Server](https://github.com/bh1848/USW-Circle-Link-Server)
- **Tech:** `Spring Boot` `Spring Security` `JWT` `Docker` `MySQL` `Redis` `AWS`

</details>

<details>
  <summary><b>수챗</b> · 2023.09 ~ 2024.10 · Backend</summary>

- 🤼‍♀️ 대학교 랜덤 채팅 및 실시간 매칭 서비스
- **Repo:** [suchat-backend](https://github.com/bh1848/suchat-backend)
- **Tech:** `Spring Boot` `Spring Security` `JWT` `MySQL` `Redis` `AWS`

</details>

<details>
  <summary><b>요분정</b> · AI / Backend</summary>

- ♻️ 딥러닝 기반 쓰레기 분류 및 포인트 적립 서비스
- **Repo:** [yobunjung-backend](https://github.com/bh1848/yobunjung-backend)
- **Tech:** `Flask` `MySQL` `ONNX` `SSE`

</details>

<details>
  <summary><b>졸음운전 방지 시스템</b> · AI / Embedded</summary>

- 😴 운전자 눈 깜빡임 감지를 통한 졸음운전 예방 솔루션
- **Repo:** [drowsy-driving-prevention](https://github.com/bh1848/drowsy-driving-prevention)
- **Tech:** `Python` `OpenCV` `Dlib`

</details>

<br/>

## 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
