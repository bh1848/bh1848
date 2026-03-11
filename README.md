<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="banner" />
</p>

# 백엔드 개발자 방혁입니다.

> **Java/Spring 기반 백엔드 개발자입니다.**  
> **인증, 캐시, 데이터 처리 성능 개선에 관심이 있습니다.**

- **Email:** bh1848@naver.com
- **Blog:** [banghyeok.blog](https://velog.io/@bh1848/posts)

## Tech Stack
<p>
  <img src="https://img.shields.io/badge/Java-111827?style=flat-square&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring%20Boot-111827?style=flat-square&logo=springboot&logoColor=white" />
  <img src="https://img.shields.io/badge/JPA%2FHibernate-111827?style=flat-square&logo=hibernate&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-111827?style=flat-square&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis-111827?style=flat-square&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS-111827?style=flat-square&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-111827?style=flat-square&logo=docker&logoColor=white" />
</p>

## Research

### [D-HASH: 분산 캐시 Hot-key 해결을 위한 동적 해싱 알고리즘](https://github.com/bh1848/D-HASH)

- Hot-key로 인한 캐시 노드 부하 집중 문제를 다뤘습니다.
- 동적 해싱 알고리즘과 재현 가능한 벤치마크 환경을 구현했습니다.
- NASA 웹 로그 기반 실험에서 Consistent Hashing 대비 **부하 불균형을 33.8% 개선**했습니다.  
  *(TIIS 2026 accepted, SCIE, 제1저자)*

<br/>

### [MySQL vs Redis 성능 비교 벤치마크](https://github.com/bh1848/mysql-redis-benchmark)

- 캐시 도입 판단을 위한 정량적 근거를 만들고자 했습니다.
- MySQL과 Redis를 연산 유형별로 비교하는 벤치마크를 설계했습니다.
- 연산 유형에 따라 평균 **7.8배 성능 차이**를 확인했습니다.  
  *(JICS 2024, KCI 제1저자)*

<br/>

## Projects

### [동구라미: 대학교 동아리 통합 관리 플랫폼](https://github.com/bh1848/USW-Circle-Link-Server)
> **2024.04 - 2025.03 | 백엔드 설계 및 API 개발 (팀 12인)**

- JWT/Redis 기반 RTR 인증 구조를 설계했습니다.
- JPA 벌크 연산으로 대량 데이터 처리 방식을 개선했습니다.
- 인증과 데이터 처리 구조를 분리해 유지보수성과 처리 효율을 높였습니다.

<br/>

### [수챗: 대학교 커뮤니티 기반 랜덤 채팅 서비스](https://github.com/bh1848/suchat-backend)
> **2023.09 - 2024.05 | 백엔드 아키텍처 및 매칭 엔진 개발 (팀 5인)**

- Redis ZSet 기반 매칭 엔진을 구현했습니다.
- JWT/Redis 기반 인증 구조를 설계했습니다.
- 매칭 로직과 인증 책임을 분리해 서비스 구조를 단순화했습니다.
