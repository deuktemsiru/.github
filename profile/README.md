<h1 align="center">득템시루</h1>

<p align="center">
  <b>마감 임박 할인 상품을 발견하고, 시루로 픽업 주문하세요</b><br/>
  구매자와 판매자를 실시간으로 연결하는 지역 기반 마감 할인 픽업 서비스
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white" alt="Kotlin"/>
  <img src="https://img.shields.io/badge/Spring Boot 4-6DB33F?style=for-the-badge&logo=springboot&logoColor=white" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Android"/>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" alt="JWT"/>
</p>

---

## 프로젝트 소개

> **"오늘 팔리지 않으면 버려지는 상품을, 가까운 소비자에게 빠르게 연결합니다."**

**득템시루**는 마감 임박 상품의 폐기를 줄이고, 사용자가 주변 매장에서 할인 상품을 픽업 주문할 수 있도록 만든 지역 커머스 서비스입니다. 구매자는 지도와 카테고리로 가까운 매장을 찾고, 장바구니와 시루 결제 흐름을 거쳐 픽업 코드 또는 QR 코드로 상품을 수령합니다. 판매자는 상품 등록, 주문 처리, 픽업 검증, 매출 분석, 알림 발송, 정산 신청까지 매장 운영에 필요한 흐름을 관리합니다.

서비스는 구매자 Android 앱, 판매자 Android 앱, Spring Boot 백엔드 API 서버로 구성되어 있습니다.

---

## Repository

| Repository | 역할 | 주요 기능 |
| --- | --- | --- |
| [`deuktemsiru_buyer`](https://github.com/deuktemsiru/deuktemsiru_buyer) | 구매자 Android 앱 | 매장 탐색, 지도, 장바구니, 주문, 픽업 QR, 길찾기, 찜, 마이페이지 |
| [`deuktemsiru_seller`](https://github.com/deuktemsiru/deuktemsiru_seller) | 판매자 Android 앱 | 홈 대시보드, 메뉴·상품 관리, 주문 처리, 픽업 검증, 매출 분석, 알림, 정산 |
| [`deuktemsiru_backend`](https://github.com/deuktemsiru/deuktemsiru_backend) | Spring Boot REST API | 인증, 매장, 상품, 장바구니, 주문, 찜, 리뷰, 알림, 정산, 모니터링 |

---

## 팀원

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/yeonwuyoo">
        <img src="https://github.com/yeonwuyoo.png" width="100px" alt="유연우"/><br/>
        <b>유연우</b>
      </a><br/>
      <sub>Android · PPT</sub><br/>
      <sub>판매자 앱 개발</sub><br/>
      <sub>매출·정산·알림 화면</sub><br/>
      <sub>발표 자료 제작</sub>
    </td>
    <td align="center">
      <a href="https://github.com/Movinggun-bit">
        <img src="https://github.com/Movinggun-bit.png" width="100px" alt="이동건"/><br/>
        <b>이동건</b>
      </a><br/>
      <sub>Backend · Android · AWS</sub><br/>
      <sub>백엔드 API 개발</sub><br/>
      <sub>구매자·판매자 앱 개발</sub><br/>
      <sub>AWS 배포</sub>
    </td>
    <td align="center">
      <a href="https://github.com/ken-jeong">
        <img src="https://github.com/ken-jeong.png" width="100px" alt="정상겸"/><br/>
        <b>정상겸</b>
      </a><br/>
      <sub>기획 · Backend · Android</sub><br/>
      <sub>백엔드 설계·구현</sub><br/>
      <sub>구매자·판매자 앱 개발</sub><br/>
      <sub>모니터링 구성</sub>
    </td>
    <td align="center">
      <a href="https://github.com/Asterisk0707">
        <img src="https://github.com/Asterisk0707.png" width="100px" alt="한동혁"/><br/>
        <b>한동혁</b>
      </a><br/>
      <sub>Android · Backend · 발표</sub><br/>
      <sub>구매자 앱 개발</sub><br/>
      <sub>엔티티 설계·알림 API</sub><br/>
      <sub>최종 발표</sub>
    </td>
    <td align="center">
      <a href="https://github.com/Ra-seungmin">
        <img src="https://github.com/Ra-seungmin.png" width="100px" alt="라승민"/><br/>
        <b>라승민</b>
      </a>
    </td>
  </tr>
</table>

---

## 서비스 구성

| 구분 | 구매자 앱 | 판매자 앱 |
| --- | --- | --- |
| 인증 | Debug 로그인, Kakao 로그인, JWT 세션 저장 | Debug 로그인, Mock 로그인, Kakao 로그인, 판매자 권한 검증 |
| 탐색 | 홈 카테고리, 검색, 지도 마커, 매장 상세 | 홈 대시보드, 판매 상품 목록, 매장 정보 |
| 거래 | 장바구니, 주문 생성, 시루 잔액 결제 UI | 주문 상태 변경, 주문 상세, 픽업 확정 |
| 픽업 | 픽업 코드, QR 코드, 카운트다운, 길찾기 | QR 스캔, 코드 직접 입력, 픽업 완료 처리 |
| 운영 | 찜, 주문 내역, 마이페이지, 알림 설정 | 메뉴 등록, 상품 등록, 매출 차트, 고객 알림, 정산 |

---

## 기술 스택

### Backend

<p>
  <img src="https://img.shields.io/badge/Kotlin 2.2.21-7F52FF?style=flat-square&logo=kotlin&logoColor=white" alt="Kotlin"/>
  <img src="https://img.shields.io/badge/Java 21-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java"/>
  <img src="https://img.shields.io/badge/Spring Boot 4.0.6-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/Spring Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white" alt="Spring Security"/>
  <img src="https://img.shields.io/badge/Spring Data JPA-59666C?style=flat-square&logo=hibernate&logoColor=white" alt="JPA"/>
  <img src="https://img.shields.io/badge/PostgreSQL 16-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/Flyway-CC0200?style=flat-square&logo=flyway&logoColor=white" alt="Flyway"/>
  <img src="https://img.shields.io/badge/springdoc--openapi 3.0.3-85EA2D?style=flat-square&logo=openapiinitiative&logoColor=black" alt="OpenAPI"/>
  <img src="https://img.shields.io/badge/Actuator-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Actuator"/>
  <img src="https://img.shields.io/badge/Micrometer-1F8DED?style=flat-square&logoColor=white" alt="Micrometer"/>
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" alt="Prometheus"/>
  <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white" alt="Grafana"/>
  <img src="https://img.shields.io/badge/Docker Compose-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker Compose"/>
  <img src="https://img.shields.io/badge/JUnit 5-25A162?style=flat-square&logo=junit5&logoColor=white" alt="JUnit 5"/>
  <img src="https://img.shields.io/badge/Testcontainers-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Testcontainers"/>
  <img src="https://img.shields.io/badge/Jacoco-2E7D32?style=flat-square&logoColor=white" alt="Jacoco"/>
  <img src="https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white" alt="Postman"/>
  <img src="https://img.shields.io/badge/Newman-FF6C37?style=flat-square&logo=postman&logoColor=white" alt="Newman"/>
  <img src="https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white" alt="k6"/>
  <img src="https://img.shields.io/badge/GitHub Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions"/>
</p>

### Android

<p>
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white" alt="Kotlin"/>
  <img src="https://img.shields.io/badge/Android Gradle Plugin 9-3DDC84?style=flat-square&logo=android&logoColor=white" alt="AGP"/>
  <img src="https://img.shields.io/badge/XML View + ViewBinding-3DDC84?style=flat-square&logo=android&logoColor=white" alt="XML View"/>
  <img src="https://img.shields.io/badge/Retrofit 2.11.0-48B983?style=flat-square&logo=square&logoColor=white" alt="Retrofit"/>
  <img src="https://img.shields.io/badge/OkHttp Authenticator-000000?style=flat-square&logoColor=white" alt="OkHttp"/>
  <img src="https://img.shields.io/badge/Kotlin Coroutines 1.8.1-7F52FF?style=flat-square&logo=kotlin&logoColor=white" alt="Coroutines"/>
  <img src="https://img.shields.io/badge/Material Components 1.13.0-757575?style=flat-square&logo=materialdesign&logoColor=white" alt="Material Components"/>
  <img src="https://img.shields.io/badge/Kakao SDK 2.21.0-FFCD00?style=flat-square&logo=kakao&logoColor=black" alt="Kakao SDK"/>
</p>

### Buyer App 추가 기술

<p>
  <img src="https://img.shields.io/badge/Google Maps SDK-4285F4?style=flat-square&logo=googlemaps&logoColor=white" alt="Google Maps"/>
  <img src="https://img.shields.io/badge/Google Location Services-4285F4?style=flat-square&logo=google&logoColor=white" alt="Location"/>
  <img src="https://img.shields.io/badge/Tmap API-1428A0?style=flat-square&logoColor=white" alt="Tmap"/>
  <img src="https://img.shields.io/badge/Navigation Component 2.9.0-3DDC84?style=flat-square&logo=android&logoColor=white" alt="Navigation"/>
  <img src="https://img.shields.io/badge/ZXing Core 3.5.3-000000?style=flat-square&logoColor=white" alt="ZXing"/>
</p>

### Seller App 추가 기술

<p>
  <img src="https://img.shields.io/badge/ZXing Android Embedded 4.3.0-000000?style=flat-square&logoColor=white" alt="ZXing"/>
  <img src="https://img.shields.io/badge/Flexbox 3.0.0-4285F4?style=flat-square&logoColor=white" alt="Flexbox"/>
  <img src="https://img.shields.io/badge/Custom Charts-FF8A00?style=flat-square&logoColor=white" alt="Charts"/>
  <img src="https://img.shields.io/badge/Local Notifications-3DDC84?style=flat-square&logo=android&logoColor=white" alt="Local Notifications"/>
</p>

---

## 시스템 아키텍처

```text
[Buyer Android App] ─┐
                     ├── REST API + JWT ──> deuktemsiru_backend ──> PostgreSQL
[Seller Android App] ┘                         │
                                               ├── Kakao API
                                               ├── Local Upload Storage
                                               ├── Flyway Migration
                                               └── Actuator / Prometheus / Grafana
```

두 Android 앱은 Kakao SDK 또는 개발용 로그인으로 백엔드 JWT를 발급받습니다. 이후 인증이 필요한 요청에는 `Authorization: Bearer {accessToken}` 헤더를 첨부하며, 401 응답 시 Refresh Token으로 Access Token을 재발급한 뒤 원 요청을 재시도합니다.

---

## 주요 기능

### 구매자 앱

| 기능 | 설명 |
| --- | --- |
| 로그인 / 온보딩 | Debug 로그인, Kakao 로그인, 약관 동의, 시루 계정 연동 안내 |
| 홈 / 카테고리 | 카테고리, 검색어, 거리 기준 매장 목록 조회 |
| 지도 탐색 | Google Maps 기반 현재 위치와 주변 매장 마커 표시 |
| 매장 상세 | 상품 목록, 할인 정보, 픽업 마감 시간, 찜 토글 |
| 장바구니 | 서버 장바구니 동기화, 수량 변경, 삭제, 전체 비우기 |
| 주문 / 결제 | 상품 주문 생성, 시루 잔액 기반 결제 UI |
| 픽업 | 주문 상태 폴링, 픽업 코드, QR 코드, 카운트다운 |
| 경로 안내 | Tmap 보행자 경로 API로 거리와 예상 시간 표시 |
| 찜 / 주문 내역 | 관심 매장 조회, 주문 목록, 주문 상세, 취소 요청 |
| 마이페이지 | 회원 정보, 시루 잔액, 통계, 알림 설정 |

### 판매자 앱

| 기능 | 설명 |
| --- | --- |
| 로그인 | Debug 로그인, Mock 로그인, Kakao 로그인, 판매자 권한 검증 |
| 홈 대시보드 | 영업 상태, 오늘 매출, 주문 현황, 활성 판매 상품 수 |
| 메뉴 등록 | 메뉴명, 원가, 설명, 알레르기 정보, 이미지 등록 |
| 판매 상품 등록 | 메뉴 기반 등록, 할인 가격, 수량, 제조 시간, 픽업 시간 설정 |
| 판매 상품 관리 | 판매중 / 품절 / 판매 종료 상태 변경, 수정, 삭제 |
| 주문 관리 | 신규, 준비 중, 픽업 대기, 완료 상태별 주문 처리 |
| 픽업 검증 | QR 스캔 또는 코드 직접 입력으로 수령 확정 |
| 매출 분석 | 주간 / 월간 / 연간 매출 차트, 결제 수단 비율, 인기 메뉴 순위 |
| 고객 알림 | 반경 기반 알림 발송, 미리보기, 발송 내역, 반경 시각화 |
| 정산 / 마이페이지 | 월별 정산 내역, 출금 신청, 계정 정보, 알림 설정 |

### 백엔드

| 기능 | 설명 |
| --- | --- |
| 인증 / 인가 | 카카오 로그인, 개발용 로그인, JWT 발급·갱신, `CONSUMER` / `SELLER` 권한 제어 |
| 매장 / 상품 | 매장 목록, 지도 마커, 매장 상세, 메뉴·판매 상품 CRUD |
| 장바구니 / 주문 | 서버 사이드 장바구니, 주문 생성·조회·취소, 판매자 주문 상태 변경 |
| 픽업 | 픽업 코드 검증, 픽업 완료 처리 |
| 찜 / 리뷰 / 알림 | 매장 찜, 리뷰 작성·삭제·조회, 사용자 알림, 판매자 고객 알림 |
| 정산 / 매출 | 판매자 매출 요약, 월별 정산 내역, 출금 신청 |
| 운영 | Flyway 마이그레이션, Swagger UI, Actuator, Prometheus, Grafana, Jacoco |

---

## 실행 방법

### 1. 백엔드 실행

PostgreSQL이 필요합니다. Docker를 사용할 경우:

```bash
docker run --name deuktemsiru-postgres \
  -e POSTGRES_DB=deuktemsiru \
  -e POSTGRES_USER=deuktemsiru \
  -e POSTGRES_PASSWORD=deuktemsiru \
  -p 5432:5432 \
  -d postgres:16-alpine
```

백엔드를 실행합니다.

```bash
cd deuktemsiru_backend
./gradlew bootRun
```

Android Studio 내장 JDK를 사용할 경우:

```bash
export JAVA_HOME="/Applications/Android Studio.app/Contents/jbr/Contents/Home"
./gradlew bootRun
```

개발용 로그인과 샘플 데이터를 사용하려면 `dev` 프로파일을 함께 사용할 수 있습니다.

```bash
./gradlew bootRun --args='--spring.profiles.active=dev'
```

### 2. Android 앱 API 키 설정

**구매자 앱** — `deuktemsiru_buyer/local.properties`

```properties
KAKAO_NATIVE_APP_KEY=your_kakao_native_app_key
MAPS_API_KEY=your_google_maps_api_key
TMAP_API_KEY=your_tmap_api_key
```

**판매자 앱** — `deuktemsiru_seller/local.properties`

```properties
KAKAO_NATIVE_APP_KEY=your_kakao_native_app_key
```

실기기나 원격 서버에 연결하려면 각 앱의 `local.properties`에 백엔드 주소를 추가합니다.

```properties
BACKEND_BASE_URL=http://your-backend-host:8080/
```

에뮬레이터에서 로컬 백엔드에 접속할 때의 기본 주소는 `http://10.0.2.2:8080/`입니다.

### 3. Android 앱 실행

Android Studio에서 `deuktemsiru_buyer` 또는 `deuktemsiru_seller`를 열고 `app` 실행 구성을 선택합니다.

CLI 빌드:

```bash
./gradlew assembleDebug
```

---

## 개발 환경 기본값

| 항목 | 값 |
| --- | --- |
| 백엔드 주소 | `http://localhost:8080` |
| 에뮬레이터 백엔드 주소 | `http://10.0.2.2:8080/` |
| Swagger UI | `http://localhost:8080/swagger-ui/index.html` |
| OpenAPI JSON | `http://localhost:8080/v3/api-docs` |
| Postman Collection | `deuktemsiru_backend/docs/postman/deuktemsiru-core.postman_collection.json` |
| Postman Environment | `deuktemsiru_backend/docs/postman/deuktemsiru-local.postman_environment.json` |
| PostgreSQL | `jdbc:postgresql://localhost:5432/deuktemsiru` |
| DB 사용자 / 비밀번호 | `deuktemsiru` / `deuktemsiru` |
| Access Token 만료 | 30분 |
| Refresh Token 만료 | 14일 |

---

## 샘플 데이터

`prod`가 아닌 환경에서 DB가 비어 있으면 시흥시 생활권 기반 샘플 데이터가 자동 생성됩니다.

| 역할 | 이름 | 닉네임 | 매장 |
| --- | --- | --- | --- |
| 구매자 | 홍길동 | 시흥득템러 | - |
| 판매자 | 김영희 | 오이도굽는집 | 오이도굽는집 |
| 판매자 | 박민준 | 배곧로스터리 | 배곧 로스터리 |
| 판매자 | 이수진 | 정왕시장분식 | 정왕시장 분식 |
| 판매자 | 최하늘 | 은행동찬찬도시락 | 은행동 찬찬도시락 |
| 판매자 | 정다은 | 목감우리반찬 | 목감 우리반찬 |

각 매장에는 주소, 좌표, 전화번호, 평점, 메뉴, 당일 판매 가능한 마감 할인 상품이 함께 생성됩니다.

---

## 도메인 참고

**API 문서 / Postman**

Swagger UI와 OpenAPI JSON은 백엔드 실행 후 아래 주소에서 확인합니다.

```text
http://localhost:8080/swagger-ui/index.html
http://localhost:8080/v3/api-docs
```

Postman에서는 `deuktemsiru_backend/docs/postman`의 컬렉션과 환경 파일을 import합니다. 전체 API 컬렉션이 필요하면 Postman에서 `http://localhost:8080/v3/api-docs`를 import해 생성합니다.

로컬 개발용 권장 플로우:

```text
Debug Login - Buyer
List Products
Add To Cart
Create Order
Debug Login - Seller
Get Store Orders
Confirm Order
Verify Pickup Code
```

**테스트 / 검증**

백엔드는 JUnit/Spring Test, Testcontainers PostgreSQL, Jacoco를 사용합니다.

```bash
cd deuktemsiru_backend
./gradlew test
./gradlew check
```

`check`는 테스트, Jacoco 리포트, 미완성 Stub 검사를 함께 실행합니다.

**주문 상태 흐름**

```text
PENDING ──▶ PREPARING ──▶ READY ──▶ COMPLETED
   │              │          │
   └──────────────┴──────────┴──▶ CANCELLED
```

**매장 카테고리**

```text
BAKERY / CAFE / RESTAURANT / GROCERY / OTHER
```
