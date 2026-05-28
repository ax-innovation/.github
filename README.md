

# 청년·직장인 금융상품 추천 서비스

금융감독원 API와 공공데이터포털 API를 활용한 금융상품 추천 및 시뮬레이션 서비스입니다.

## 저장소 구조
| 저장소 | 설명 |
|---|---|
| [crawler](https://github.com/ax-innovation/crawler) | 금감원 API 데이터 수집기 (Python) |
| [server](https://github.com/ax-innovation/server) | REST API 서버 (Spring Boot) |
| [frontend](https://github.com/ax-innovation/frontend) | 프론트엔드 (React) |

## 실행 방법

### 1. 필수 설치
- Python 3.11+
- JDK 17
- Node.js 20 LTS
- MySQL 8.0

### 2. DB 설정
```sql
mysql -u root -p
CREATE DATABASE findb CHARACTER SET utf8mb4;
```

### 3. Python 수집기 (crawler)
```bash
cd crawler
cp run_all.example.py run_all.py
# run_all.py 열어서 API 키, DB 비밀번호 입력
pip install requests pymysql
python run_all.py
```

### 4. Spring Boot (server)
```bash
cd server
cp src/main/resources/application.example.yml src/main/resources/application.yml
# application.yml 열어서 DB 비밀번호 입력
./gradlew bootRun
```

### 5. React (frontend)
```bash
cd frontend
cp .env.example .env.production
npm install
npm run dev
```
