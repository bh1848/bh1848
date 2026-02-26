<p align="center">
  <img src="./assets/banner.svg" width="100%" alt="banner" />
</p>

# 🐶 안녕하세요. 백엔드 개발자 방혁입니다. 

> **"보안 및 성능 최적화와 안정적인 아키텍처 설계"**

사용자 경험을 최우선으로 생각하며, 특히 대용량 트래픽 처리와 시스템 아키텍처 및 보안에 관심을 가지고 있습니다. 
- **Email:** bh1848@naver.com
- **Blog:** [hzeror.blog](https://hzeror.netlify.app/)

### 🥷 Skills
**Main**
<p>
  <img src="https://img.shields.io/badge/Java-111827?style=flat-square&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring%20Boot-111827?style=flat-square&logo=springboot&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring%20Security-111827?style=flat-square&logo=springsecurity&logoColor=white" />
  <img src="https://img.shields.io/badge/JPA%2FHibernate-111827?style=flat-square&logo=hibernate&logoColor=white" />
  <img src="https://img.shields.io/badge/JUnit5-111827?style=flat-square&logo=junit5&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-111827?style=flat-square&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis-111827?style=flat-square&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-111827?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS-111827?style=flat-square&logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-111827?style=flat-square&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Postman-111827?style=flat-square&logo=postman&logoColor=white" />
</p>

**Sub**
<p>
  <img src="https://img.shields.io/badge/OpenCV-111827?style=flat-square&logo=opencv&logoColor=white" />
  <img src="https://img.shields.io/badge/Flask-111827?style=flat-square&logo=flask&logoColor=white" />
</p>

<br/>

## Featured Research

### [📊 D-HASH: 분산 캐시 Hot-key 해결을 위한 동적 해싱 알고리즘](https://github.com/bh1848/D-HASH)
> **대규모 트래픽 환경의 특정 노드 부하 집중 문제를 해결하는 알고리즘 연구**

- **Publication**: [📝 TIIS 2026 게재 예정 (SCIE 제1저자)](https://doi.org/10.3837/tiis.2026.xx.xxx)
- **Impact**: **부하 불균형 33.8% 개선** (NASA 웹 로그 기반 Consistent Hashing 대비)

#### **💫 Key Achievements & Troubleshooting**
- **[연산 효율 최적화]** MD5 병목을 `xxHash64`로 대체하여 **속도 20배 향상 및 메모리 50% 절감**
- **[안정성 확보]** Guard Phase 설계를 통해 노드 전환 시 발생하는 **Latency Spike 방어**
- **[신뢰도 검증]** 비동기 I/O 모델 기반 **180,000 OPS급 고부하 테스트 환경** 구축 및 검증
- **[정합성 유지]** 분산 환경 데이터 일관성을 위한 **Write-Primary 정책** 설계

[[**트러블슈팅 확인하기**]](https://github.com/bh1848/D-HASH/blob/main/docs/REPORT_KR.md#5-트러블슈팅)

<br/>

### [⚖️ MySQL vs Redis 성능 비교 벤치마크](https://github.com/bh1848/mysql-redis-benchmark)
> **저장 매체 및 데이터 구조 차이에 따른 기술적 의사결정 근거 수립 연구**

- **Publication**: [📜 JICS 2024 게재 (KCI 제1저자)](https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003098301)
- **Impact**: 연산 유형별 성능 차이(평균 7.8배) 수치화를 통해 **캐시 도입의 객관적 기술 근거 마련**

#### **💫 Key Achievements & Troubleshooting**
- **[측정 신뢰도 확보]** `AbstractBatchExperiment` 추상화 및 Connection Warm-up 도입으로 **환경 간섭 및 측정 오차 제거**
- **[정밀 지표 도출]** `System.currentTimeMillis()`의 오차를 산술 평균 방식으로 보완하여 **0.17ms 단위의 정밀 데이터 확보**
- **[데이터 구조 분석]** B-Tree와 Hash 구조 차이에 따른 연산 효율 검증으로 **인프라 설계 시 최적의 저장소 선택 가이드라인 수립**

[[**트러블슈팅 확인하기**]](https://github.com/bh1848/mysql-redis-benchmark#4-트러블슈팅)

<br/>

## Impactful Projects

### [🌕 동구라미: 대학교 동아리 통합 관리 플랫폼](https://github.com/bh1848/USW-Circle-Link-Server)
> **교내 동아리 정보 파편화 해결 및 운영 효율화를 위한 중앙 관리 시스템**

- **Core**: JWT/Redis RTR 기반 보안 아키텍처 구축 및 QueryDSL 성능 최적화

#### **💫 Key Achievements & Troubleshooting**
- **[DB 성능 최적화]** Bulk 연산 및 QueryDSL 동적 쿼리 최적화로 **DB 쿼리 실행 수 90% 이상 절감 (2N+2 → 10 고정)**
- **[구조 설계 개선]** 책임 연쇄(CoR) 패턴 도입으로 복잡한 인증 분기 로직의 **유지보수성 및 확장성 확보**
- **[인프라 보안 강화]** S3 Presigned URL 도입을 통한 **서버 부하 분산** 및 공통 인터셉터 단의 **보안 취약점(XSS, 부정 파일) 방어**
- **[운영 가시성 확보]** MDC 기반 로그 추적 시스템 구축으로 분산 환경에서의 **장애 대응 효율 개선**

[[**트러블슈팅 확인하기**]](https://github.com/bh1848/USW-Circle-Link-Server#6-트러블슈팅)

<br/>

### [💬 수챗: 대학교 커뮤니티 기반 랜덤 채팅 서비스](https://github.com/bh1848/suchat-backend)
> **교내 구성원 인증 기반의 실시간 1:1 익명 채팅 서비스**

- **Core**: Redis ZSet 기반 매칭 엔진 및 실시간 비동기 알림 시스템 구축

#### **💫 Key Achievements & Troubleshooting**
- **[매칭 엔진 최적화]** 동기 방식의 병목을 해결하기 위해 **Redis ZSet과 `@Async` 비동기 조합**을 도입하여 처리 효율 극대화
- **[데이터 정합성 보장]** 분산 환경에서의 매칭 상태 불일치를 **Redis 원자적(Atomic) 연산**으로 해결하여 시스템 무결성 확보
- **[보안 체계 강화]** Redis TTL 기반 **RTR(Refresh Token Rotation)** 적용으로 토큰 탈취 리스크 방어 및 인증 파이프라인 고도화
- **[리소스 관리 자동화]** `@Scheduled` 배치 기반의 데이터 클리닝 프로세스를 구축하여 **메인 DB의 무결성 및 성능 유지**

[[**트러블슈팅 확인하기**]](https://github.com/bh1848/suchat-backend/#6-트러블슈팅)

<br/>

### 🏆 Baekjoon Solved Rank
<img
  src="https://mazassumnida.wtf/api/v2/generate_badge?boj=bh1848"
  height="150"
  alt="BOJ Badge"
/>
