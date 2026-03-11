<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="banner" />
</p>

# 백엔드 개발자 방혁입니다.

> **Java/Spring 기반 백엔드 개발자입니다.**  
> 인증, 캐시, 데이터 처리 병목을 **측정하고 개선하는 시스템 설계**에 관심이 있습니다.

- **Email**: bh1848@naver.com  
- **Blog**: https://velog.io/@bh1848/posts



## Featured Work

### **D-HASH: 분산 캐시 Hot Key 완화를 위한 동적 해싱 알고리즘**

분산 캐시 환경에서 **Hot key로 인한 노드 부하 집중 문제**를 해결하기 위해  
동적 해싱 기반 라우팅 알고리즘을 설계하고, 재현 가능한 실험 환경을 구현했습니다.

- Hot key 감지와 read 전환을 분리하는 **동적 라우팅 구조 설계**
- Consistent Hashing 기반 캐시 라우팅 환경 재현
- NASA 웹 로그 기반 실험 환경 구축
- Consistent Hashing 대비 **부하 불균형 33.8% 개선**

**SCIE Journal (TIIS 2026 accepted)**  
**DOI**: 추후 입력

<br/>


## Projects

### **동구라미 — 대학교 동아리 통합 관리 플랫폼**
> **2024.04 – 2025.03 | Backend | 팀 12명**

- JWT + Redis 기반 **RTR(Refresh Token Rotation) 인증 구조 설계**
- JPA 벌크 연산을 활용한 **대량 데이터 처리 성능 개선**
- 인증 로직과 도메인 로직을 분리해 **서비스 구조 단순화**
- 인증 및 데이터 처리 책임을 명확히 분리해 **유지보수성 개선**

**Repository**: https://github.com/bh1848/USW-Circle-Link-Server

<br/>

### **수챗 — 대학교 커뮤니티 기반 랜덤 채팅 서비스**
> **2023.09 – 2024.05 | Backend | 팀 5명**

- Redis ZSet 기반 **랜덤 매칭 엔진 구현**
- JWT + Redis 기반 **인증 구조 설계**
- 매칭 로직과 인증 로직을 분리해 **서비스 책임 구조 단순화**
- Redis 자료구조를 활용해 **매칭 처리 효율 개선**

**Repository**: https://github.com/bh1848/suchat-backend

<br/>


## Research

- [**MySQL과 Redis의 데이터 처리 성능 비교 평가**](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)  
  *Journal of KSIIS (KCI), 2024 — 제 1저자*  
  DOI: 10.7472/jksii.2024.25.3.35

<br/>

## Tech Stack

**Backend**  
Java, Spring Boot, JPA / Hibernate

**Data**  
MySQL, Redis

**Infra**  
Docker, AWS
