# 👋 Hi, I'm Bang Hyeok
Backend Developer & Systems Researcher specializing in **Spring Boot, Security, and Scalable Architecture.**
분산 환경에서의 성능·부하 문제를 해결하는 기술과 안정적인 인증·보안 구조를 갖춘 백엔드 시스템 설계에 집중하고 있습니다.

---

## 📖 Research / Publications
- **MySQL과 Redis의 데이터 처리 성능 비교 평가**  
  *인터넷정보학회논문지 (Journal of Internet Computing and Services, JICS)*, Vol.25, No.3, pp. 35-41, 2024  
  DOI: [10.7472/jksii.2024.25.3.35](https://doi.org/10.7472/jksii.2024.25.3.35)  
  - MySQL(RDBMS)과 Redis(NoSQL) 성능을 삽입·조회·삭제 속도로 비교
  - NoSQL 기반 캐싱 전략의 기술적 근거 제시  
  - [mysql-redis-benchmark](https://github.com/bh1848/mysql-redis-benchmark)
 
- **D-HASH: Dynamic Hot-key Aware Scalable Hashing**
  *인터넷정보학회논문지 (Journal of Internet Computing and Services, JICS)*
  DOI:
  - Consistent Hashing 기반 분산 캐시 시스템에서의 핫키 집중 문제 해결을 목표로 한 라우팅 알고리즘 개발
  - 실시간 핫키 감지 및 다중 노드 라우팅 전략을 활용한 부하 분산 향상 연구
  - Redis 기반 실험 환경에서 Throughput, Latency, Load Stddev을 중심으로 성능 평가
  - [dhash-routing-evaluation](https://github.com/bh1848/dhash-routing-evaluation)
    
---

## 💡 Selected Projects

### [Donggurami-Backend](https://github.com/bh1848/donggurami-backend)
대학교 동아리 관리 플랫폼 (실서비스 운영 중)  
**Role:** Backend Developer
- 관리자(Admin) 및 공지(Notice) API 개발  
- Spring Security + JWT 인증/인가 구조 설계 및 구현 
- Access / Refresh Token 발급·검증 및 인증 필터 작성  
- Redis 연동 및 캐싱·세션·토큰 저장 구조 구성 
- Multipart 이미지 업로드 처리 및 파일 검증/저장 로직 구현

### [Suchat-Backend](https://github.com/bh1848/suchat-backend)
대학교 랜덤 채팅 서비스 백엔드  
**Role:** Backend Developer  
- Spring Boot 기반 회원가입·로그인 API 개발
- Spring Security + JWT 인증/인가 구조 설계 및 구현  
- Access / Refresh Token 발급·검증 및 인증 필터 작성  
- 사용자 상태 관리(온라인/오프라인) 및 랜덤 매칭 알고리즘 개발  
- JWT를 처음 독학하며 인증 흐름(필터 → Provider → Token 처리) 전체 설계 경험    

### [Yobunjung-Backend](https://github.com/bh1848/yobunjung-backend)
AI 기반 분리수거 가이드 & 재활용 로그 시스템  
**Role:** Backend Developer
- Flask 기반 백엔드 서버 및 전체 REST API 개발  
- ONNX 모델 연동하여 쓰레기 이미지 분류 inference 구현  
- SSE를 활용한 실시간 피드백 스트리밍 로직 구축  
- SQLAlchemy 기반 DB 스키마 설계 및 모델링  
- 비동기 이벤트 처리 흐름 구성 및 실시간 응답 구조 구현  

### [Drowsy-Driving-Prevention](https://github.com/bh1848/drowsy-driving-prevention)
운전자 졸음 감지 시스템  
**Role:** Computer Vision Developer  
- Python + OpenCV 기반 실시간 눈 감김 감지 알고리즘 구현  
- 얼굴·눈 ROI 추출 및 EAR 기반 졸음 판별 로직 작성  
- 영상 처리 전체 흐름 및 예외 처리 구현  
- 경고 이벤트 트리거 로직 구현
  
---

## 🛠 Tech Stack
- **Languages**: Java, Python
- **Backend Frameworks**: Spring Boot, Flask
- **Database**: MySQL, Redis
- **Security / Auth**: Spring Security, JWT
- **Infrastructure**: AWS (EC2, RDS, S3)
- **Tools & Libraries**: Git, Gradle, JPA, OpenCV, ONNX Runtime

---

## 📫 Contact
- 📧 Email: bh1848@naver.com 
- 🐙 GitHub: [bh1848](https://github.com/bh1848)
