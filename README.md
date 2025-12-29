<p align="center">
  <img src="./assets/banner.svg" alt="BangHyeok banner" />
</p>

<h1 align="center">방혁 · BangHyeok</h1>

<p align="center">
  Spring Boot 백엔드 · API 설계 · Redis/분산 캐시 라우팅 실험
</p>

<p align="center">
  <a href="mailto:bh1848@naver.com">Email</a>
  ·
  <a href="https://github.com/bh1848">GitHub</a>
  ·
  <a href="#">Blog</a>
  ·
  <a href="#">CV</a>
</p>

---

## About

- **백엔드 개발**(Spring Boot 중심)과 **Redis 기반 분산 시스템 실험**을 병행합니다.
- “기능 구현”보다 **병목을 찾고, 측정하고, 재현 가능하게 정리하는 방식**을 좋아합니다.
- 관심사: Distributed Cache, Load Balancing, Hashing/Routing, Performance Engineering

---

## Research

| Title | Status | One-liner | Links |
|---|---|---|---|
| **MySQL–Redis Benchmark** | Published (2024) | 배치 기반 INSERT/SELECT/DELETE 지연시간 비교 실험 및 분석 | Repo · KCI |
| **D-HASH: Dynamic Hot-key Aware Scalable Hashing** | Under Review | 핫 키로 인한 부하 집중을 완화하는 **라우팅 레이어** 중심 해싱 기법 + Redis 실험 | Repo |

---

## Projects

| Project | Stack | What I did | Links |
|---|---|---|---|
| **dhash-routing-evaluation** | Python · Docker · Redis | 5노드 Redis 컨테이너 환경에서 TPS/Latency/P95/P99/Load Stddev 측정 자동화 | https://github.com/bh1848/dhash-routing-evaluation |
| **mysql-redis-benchmark** | Python · MySQL · Redis | DB vs Cache 비교 실험 스크립트/결과 정리 | https://github.com/bh1848/mysql-redis-benchmark |
| **yobunjung-backend** | Flask · Redis · MySQL | 인증/인가, API 설계, 캐시/DB 연동, 운영을 고려한 구조화 | https://github.com/bh1848/yobunjung-backend |
| **su-chat** | Spring Boot · JPA | 채팅 백엔드(도메인/테스트/구조 개선) | https://github.com/bh1848/su-chat |

---

## Tech

**Backend**  
Java, Spring Boot, JPA/Hibernate, REST API, JWT Auth

**Data / Infra**  
MySQL, Redis, Docker, Linux, WSL2

**Experiment / Tools**  
Python, profiling/benchmarking, reproducibility (seed/env logging), metrics & visualization

---

## What I’m focusing on now

- Redis 기반 분산 캐시 라우팅 실험 고도화 (membership 변화/동적 시나리오, baseline 확장)
- 백엔드 취업 대비: 인증/인가, 트러블슈팅, 운영/성능 최적화 경험 축적

---

## Contact

- Email: **bh1848@naver.com**
- GitHub: https://github.com/bh1848
- (Optional) Blog / Portfolio: 링크 추가
