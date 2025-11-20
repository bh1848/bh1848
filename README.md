# 👋 Hi, I'm Bang Hyeok  
**Backend Developer specializing in Spring Boot and Security.**  
안정적이고 확장 가능한 백엔드 시스템을 설계하고,  
신뢰할 수 있는 인증·보안 구조를 구축하는 데 집중하고 있습니다.

---

## 📖 Research Experience  

### **MySQL–Redis Performance Comparison**  
*Journal of Internet Computing and Services (JICS), Vol.25, No.3, pp. 35-41, 2024*  
DOI: [10.7472/jksii.2024.25.3.35](https://doi.org/10.7472/jksii.2024.25.3.35)  
- RDBMS(MySQL) vs NoSQL(Redis) 삽입·조회·삭제 성능 비교  
- 대규모 서비스 캐싱 전략 수립을 위한 성능 근거 제시  
- **Code:** https://github.com/bh1848/mysql-redis-benchmark

### **D-HASH: Dynamic Hot-key Aware Scalable Hashing** *(Under Review)*  
- Consistent Hashing 기반 분산 캐시의 핫키 스큐 문제 해결을 목표로 설계  
- 실시간 핫키 감지 + 결정적 다중 노드 라우팅 전략 적용  
- Redis 테스트베드 실험을 통해 Throughput, Latency, Load Stddev 평가  
- **Code:** https://github.com/bh1848/dhash-routing-evaluation

---

## 💡 Selected Projects  

### 🚀 Donggurami-Backend  
Repository: https://github.com/bh1848/donggurami-backend  
수원대학교 동아리 운영·관리 통합 플랫폼 (실서비스 운영 중)  
**Role:** Backend Developer  
- Spring Security + JWT 기반 인증/인가 전체 구조 설계 및 구현  
- Redis 기반 Refresh Token 스토리지 및 캐싱 구조 구축  
- 관리자(Admin), 공지(Notice), 동아리 지원(Application) 도메인 API 개발  
- AWS S3 기반 이미지 업로드 및 파일 관리 로직 구현  
- AWS EC2 · RDS · NGINX 기반 서버 인프라 구성 및 배포  

---

### 💬 Suchat-Backend  
Repository: https://github.com/bh1848/suchat-backend  
수원대학교 실시간 랜덤 채팅 서비스  
**Role:** Backend Developer  
- Spring Boot 기반 회원가입/로그인/인증 API 개발  
- JWT 인증 플로우(필터 → Provider → Token) 직접 설계 및 적용  
- Redis Sorted Set 기반 랜덤 매칭 알고리즘 개발   

---

### 🗑️ Yobunjung-Backend  
Repository: https://github.com/bh1848/yobunjung-backend  
AI 기반 분리수거 가이드 & 재활용 로그 플랫폼  
**Role:** Backend Developer   
- Flask 기반 REST API 전체 설계 및 구현  
- ONNX Runtime 기반 이미지 분류 모델 연동 및 추론 파이프라인 구성  
- SSE 기반 실시간 분류 결과 스트리밍 기능 개발  
- MySQL/SQLite 기반 재활용 로그·사용자·쓰레기통 데이터 모델링 및 CRUD 구현

---

### 👀 Drowsy-Driving-Prevention  
Repository: https://github.com/bh1848/drowsy-driving-prevention  
실시간 졸음 운전 감지 프로토타입 시스템  
**Role:** Python · Computer Vision Developer     
- Python + OpenCV 기반 얼굴·눈 랜드마크 실시간 추적 구현  
- EAR(Eye Aspect Ratio) 기반 졸음 감지 알고리즘 설계  
- 졸음 발생 시 Arduino 모듈로 경고 신호 전송하는 시리얼 통신 처리  
- 영상 처리·알고리즘·UI·하드웨어 연동을 하나의 흐름으로 통합

---

## 🛠 Tech Stack  
- **Languages:** Java, Python  
- **Backend:** Spring Boot, Flask  
- **Security:** Spring Security, JWT  
- **Database:** MySQL, Redis  
- **Infra:** AWS (EC2, RDS, S3), NGINX  
- **Tools:** Git, Gradle, JPA, ONNX Runtime, OpenCV  

---

## 📫 Contact  
- 📧 Email: bh1848@naver.com  
- 🐙 GitHub: https://github.com/bh1848
