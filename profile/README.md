# 청년·직장인 금융상품 추천 서비스

금융감독원 API와 공공데이터포털 API를 활용한 금융상품 추천 및 시뮬레이션 서비스입니다.

## 저장소 구조
| 저장소 | 설명 |
|---|---|
| [crawler](https://github.com/ax-innovation/crawler) | 금감원 API 데이터 수집기 (Python) |
| [server](https://github.com/ax-innovation/server) | REST API 서버 (Spring Boot) |
| [frontend](https://github.com/ax-innovation/frontend) | 프론트엔드 (React) |

---

## 시작하기

### 1. 저장소 받아오기
```bash
git clone https://github.com/ax-innovation/crawler.git
git clone https://github.com/ax-innovation/server.git
git clone https://github.com/ax-innovation/frontend.git
```

### 2. API 키 발급
| API | 발급처 | 비고 |
|---|---|---|
| 금감원 API | https://finlife.fss.or.kr → 오픈API → 인증키 신청 | 즉시 발급 |
| 공공데이터포털 | https://www.data.go.kr → 회원가입 후 신청 | 즉시~1일 |

### 3. 필수 프로그램 설치
- Python 3.11+
- JDK 17
- Node.js 20 LTS
- MySQL 8.0

### 4. DB 설정
```bash
mysql -u root -p
```
```sql
CREATE DATABASE findb CHARACTER SET utf8mb4;
```

### 5. Python 수집기 (crawler)
```bash
cd crawler
cp run_all.example.py run_all.py
# run_all.py 열어서 API 키, DB 비밀번호 입력
pip install requests pymysql
python run_all.py
```

### 6. Spring Boot (server)
```bash
cd server
cp src/main/resources/application.example.yml src/main/resources/application.yml
# application.yml 열어서 DB 비밀번호 입력
./gradlew bootRun
```

### 7. React (frontend)
```bash
cd frontend
cp .env.example .env.production
npm install
npm run dev
# 브라우저에서 http://localhost:5173 접속
```

---

## 협업 방법

### 새 기능 개발할 때
```bash
# 1. 최신 코드 받아오기
git pull origin main

# 2. 새 브랜치 만들기
git checkout -b feature/본인이름-작업내용
# 예시: git checkout -b feature/jihun-loan-filter

# 3. 코드 수정 후 저장
git add .
git commit -m "어떤 기능을 추가/수정했는지 설명"

# 4. GitHub에 올리기
git push origin feature/본인이름-작업내용

# 5. GitHub에서 Pull Request 생성 → 팀원 검토 → main에 합치기
```

### 팀원이 올린 코드 받아오기
```bash
git pull origin main
```

### 이전 버전으로 되돌리기
```bash
# 커밋 목록 확인
git log --oneline

# 특정 버전으로 되돌리기
git revert 커밋아이디
```
