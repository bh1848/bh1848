<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="banner" />
</p>

# 🐶 안녕하세요. 백엔드 개발자 방혁입니다.

### 🔙 Backend Developer
- **Spring Boot**를 주력으로 안정적이고 확장 가능한 API를 설계하고 구현합니다.
- JWT 기반 인증/인가, MySQL/JPA, Redis를 활용한 서비스 개발 및 운영 경험이 있습니다.
- 대규모 트래픽 처리를 위한 시스템 아키텍에 관심이 많으며, **Redis 분산 캐시 라우팅(D-HASH) 연구**를 통해 성능 최적화를 검증한 경험이 있습니다.

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
    <b>D-HASH: 분산 캐시 Hot-key 해결 알고리즘 (SCIE)</b>
    <img src="https://img.shields.io/badge/SCIE-Accepted-0066CC?style=flat-square&logo=googlescholar&logoColor=white"/>
    <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
    <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>
  </summary>

<br>

**Hot-key로 인한 서버 부하 불균형을 해결하는 동적 라우팅 기법**

- **Problem:** 특정 키 요청 증가(Hot-key) 시 발생하는 단일 노드 과부하
- **Solution:** 실시간 접근 빈도 감지 및 **동적 라우팅 알고리즘** 개발
- **Impact:** Consistent Hashing 대비 **부하 표준편차 33.8% 감소**
- **Role:** 알고리즘 개발, 실험 설계·구현·분석, 논문 작성 (제1저자)
- **Links:**
  - 🐙 [**GitHub Repository**](https://github.com/bh1848/D-HASH)
  - 📝 [**Paper (SCIE / TIIS 2026)**](https://doi.org/10.3837/tiis.2026.xx.xxx)

</details>

<details>
  <summary>
    <b>MySQL vs Redis 성능 비교 벤치마크 (KCI)</b>
    <img src="https://img.shields.io/badge/KCI-Published-00C7B7?style=flat-square"/>
    <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
    <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>
  </summary>

<br>

**RDBMS(MySQL)와 NoSQL(Redis)의 실제 응답 속도(Latency) 비교·분석**

- **Goal:** 데이터 연산 유형에 따른 DB별 성능 비교
- **Result:** Redis가 MySQL 대비 **평균 7.8배 빠름**을 입증 (1.39ms vs 0.17ms)
- **Insight:** 실제 시스템에서의 캐시 도입 기준 확립
- **Role:** 실험 설계·구현·분석 (제1저자)
- **Links:**
  - 🐙 [**GitHub Repository**](https://github.com/bh1848/mysql-redis-benchmark)
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
