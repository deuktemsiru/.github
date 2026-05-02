# 득템시루

**득템시루**는 마감 임박 할인 상품을 합리적인 가격에 구매하고, 매장은 남은 재고를 효율적으로 소진할 수 있도록 연결하는 픽업 예약 서비스입니다.

구매자는 카카오 로그인 후 지도와 카테고리 탐색으로 주변 마감 할인 매장을 찾고, 상품을 장바구니에 담아 픽업을 예약합니다. 판매자는 메뉴와 판매 상품을 등록하고, 주문 접수부터 픽업 검증, 매출 분석, 정산까지 한 앱에서 처리합니다.

---

## Repository 구성

| Repository | 역할 |
| --- | --- |
| [`deuktemsiru_buyer`](https://github.com/deuktemsiru/deuktemsiru_buyer) | 매장 탐색 · 지도 · 경로 안내 · 장바구니 · 주문 · 찜 · 마이페이지를 제공하는 구매자 Android 앱 |
| [`deuktemsiru_seller`](https://github.com/deuktemsiru/deuktemsiru_seller) | 홈 대시보드 · 메뉴·상품 관리 · 주문 처리 · 픽업 검증 · 매출 분석 · 고객 알림을 관리하는 판매자 Android 앱 |
| [`deuktemsiru_backend`](https://github.com/deuktemsiru/deuktemsiru_backend) | 카카오 인증 · JWT · 매장 · 주문 · 정산 · 모니터링 API를 제공하는 Spring Boot 백엔드 |
| [`.github`](https://github.com/deuktemsiru/.github) | 조직 프로필 문서 (현재 Repository) |

---

## 시스템 아키텍처

```
[구매자 앱]                [판매자 앱]
 Kotlin / Android           Kotlin / Android
 Retrofit + JWT              Retrofit + JWT
      │                           │
      └──────────┬────────────────┘
                 ▼
     deuktemsiru_backend
      Spring Boot 4 / Kotlin
      Spring Security + JWT
                 │
      ┌──────────┼──────────┐
      ▼          ▼          ▼
  H2 (개발)  PostgreSQL  Kakao API
              (운영)    (사용자 인증)
                 │
      ┌──────────┘
      ▼
  Prometheus + Grafana (모니터링)
```

두 앱은 카카오 SDK로 로그인한 뒤 백엔드로부터 JWT를 발급받습니다. 이후 모든 요청은 OkHttp Interceptor를 통해 `Authorization: Bearer {accessToken}` 헤더를 자동으로 첨부합니다.

---

## 주요 기능

### 구매자 앱

| 기능 | 설명 |
| --- | --- |
| 카카오 로그인 | Kakao SDK로 로그인 후 백엔드 JWT 발급 및 세션 저장 |
| 홈 / 카테고리 탐색 | 베이커리 · 카페 · 음식점 · 마트 등 카테고리별 마감 할인 매장 목록 |
| 지도 탐색 | Google Maps 위에 현재 위치와 매장 마커 표시 |
| 경로 안내 | Tmap 보행자 경로로 거리 · 소요 시간 안내 |
| 매장 상세 | 할인 상품 목록, 남은 픽업 시간, 찜 토글 |
| 장바구니 / 주문 | 상품 담기, 수량 조정, 예상 절감 금액 확인 후 픽업 주문 생성 |
| 시루 결제 | 시루 계정 연동 후 잔액 차감 방식 결제 |
| 픽업 확인 | 주문 완료 후 픽업 코드 · 주문 상세 확인 |
| 찜 · 주문 내역 | 관심 매장 저장, 진행 중 / 완료된 주문 이력 조회 |
| 마이페이지 | 회원 정보, 등급, 수신 알림 목록 |

### 판매자 앱

| 기능 | 설명 |
| --- | --- |
| 홈 대시보드 | 매장 운영 상태, 오늘 매출, 주문 현황, 활성 판매 상품 수 |
| 메뉴 등록 | 단계별 입력 (이름 · 가격 · 할인율 · 수량 · 픽업 시간 · 알레르기 정보 · 이미지) |
| 판매 상품 관리 | 등록 메뉴 기반 당일 판매 상품 생성, 상태 변경, 삭제 |
| 주문 관리 | 신규 → 준비 중 → 픽업 대기 → 완료 탭 전환, 주문 상세 바텀시트 |
| 픽업 검증 | QR 스캔 또는 코드 직접 입력으로 픽업 완료 처리 |
| 매출 분석 | 주간 / 월간 / 연간 Bar · Pie 차트, 인기 메뉴 순위 |
| 가게 정보 | 매장 설명 · 연락처 수정, 메뉴 목록 관리 |
| 고객 알림 | 반경 내 구매자에게 알림 발송 · 발송 내역 조회 |
| 정산 | 월별 정산 내역 확인 · 출금 신청 |

### 백엔드

| 기능 | 설명 |
| --- | --- |
| 카카오 인증 / JWT | 카카오 Access Token으로 로그인 또는 자동 회원가입, Access / Refresh Token 발급 및 갱신 |
| 매장 / 찜 | 카테고리별 매장 목록, 매장 상세, 찜 등록 / 해제 |
| 장바구니 | 서버 사이드 장바구니 추가 · 조회 · 삭제 · 비우기 |
| 주문 | 구매자 주문 생성, 목록, 상세, 취소 |
| 판매자 | 메뉴 · 판매 상품 CRUD, 주문 상태 변경, 픽업 코드 검증 |
| 매출 / 정산 | 주간 · 월간 · 연간 매출 통계, 월별 정산 내역, 출금 신청 |
| 알림 | 구매자 알림 목록 · 읽음 처리, 판매자 고객 알림 발송 |
| 모니터링 | Prometheus + Grafana로 HTTP · DB · JVM · 비즈니스 메트릭 수집 |
| 샘플 데이터 | H2 DB가 비어 있을 때 시흥시 권역 기반 샘플 매장 · 메뉴 · 상품 자동 생성 |

---

## 기술 스택

### Android 공통

| 구분 | 기술 |
| --- | --- |
| 언어 | Kotlin |
| UI | XML View, ViewBinding, Material Components 1.13.0 |
| 네트워크 | Retrofit 2.11.0, Gson Converter, OkHttp Interceptor |
| 비동기 | Kotlin Coroutines 1.8.1 |
| 소셜 로그인 | Kakao SDK User 2.21.0 |
| 빌드 | Gradle Kotlin DSL, Android Gradle Plugin |

### 구매자 앱 추가

| 구분 | 기술 |
| --- | --- |
| 아키텍처 | Single Activity + Fragment, Navigation Component 2.9.0 |
| 지도 | Google Maps SDK 19.0.0, Play Services Location 21.3.0 |
| 경로 | Tmap 보행자 경로 API |

### 판매자 앱 추가

| 구분 | 기술 |
| --- | --- |
| 아키텍처 | LoginActivity + MainActivity(탭) + 기능별 별도 Activity |
| QR 스캔 | ZXing Android Embedded 4.3.0 |
| 레이아웃 | Google Flexbox 3.0.0 |
| 커스텀 UI | BarChartView, PieChartView, RadiusMapView (자체 구현) |

### 백엔드

| 구분 | 기술 |
| --- | --- |
| 언어 / 런타임 | Kotlin 2.2.21 / Java 21 |
| 프레임워크 | Spring Boot 4.0.6 |
| 데이터 | Spring Data JPA, Hibernate, H2 (개발), PostgreSQL (운영) |
| 보안 | Spring Security 6, JWT Bearer Token |
| API 문서 | springdoc-openapi 3.0.3 |
| 모니터링 | Spring Boot Actuator, Micrometer, Prometheus, Grafana |
| 빌드 / CI | Gradle Kotlin DSL, GitHub Actions |
| 컨테이너 | Docker, Docker Compose |

---

## 전체 실행 방법

### 1. 백엔드 실행

```bash
cd deuktemsiru_backend
export JAVA_HOME="/Applications/Android Studio.app/Contents/jbr/Contents/Home"
./gradlew bootRun
```

### 2. Android 앱 API 키 설정

각 앱 프로젝트 루트의 `local.properties`에 필요한 키를 추가합니다.

**구매자 앱 (`deuktemsiru_buyer/local.properties`)**

```properties
KAKAO_NATIVE_APP_KEY=your_kakao_native_app_key
MAPS_API_KEY=your_google_maps_api_key
TMAP_API_KEY=your_tmap_api_key
```

**판매자 앱 (`deuktemsiru_seller/local.properties`)**

```properties
KAKAO_NATIVE_APP_KEY=your_kakao_native_app_key
```

### 3. Android Studio에서 앱 실행

Android Studio에서 `deuktemsiru_buyer` 또는 `deuktemsiru_seller` 프로젝트를 열고 `app` 실행 구성을 실행합니다.

Android Emulator에서 로컬 백엔드에 접속할 때는 `http://10.0.2.2:8080/`을 사용합니다. 실기기나 원격 서버에 연결하려면 `local.properties`에 아래 항목을 추가합니다.

```properties
BACKEND_BASE_URL=http://your-backend-host:8080/
```

---

## 샘플 데이터

백엔드 최초 실행 시 H2 DB가 비어 있으면 시흥시 생활권을 기반으로 한 샘플 데이터가 자동 생성됩니다.

| 역할 | 이름 (닉네임) | 매장 | 카테고리 |
| --- | --- | --- | --- |
| 구매자 | 홍길동 (시흥득템러) | — | — |
| 판매자 | 김영희 (오이도굽는집) | 오이도 굽는집 | BAKERY |
| 판매자 | 박민준 (배곧로스터리) | 배곧 로스터리 | CAFE |
| 판매자 | 이수진 (정왕시장분식) | 정왕시장 분식 | RESTAURANT |
| 판매자 | 최하늘 (은행동찬찬도시락) | 은행동 찬찬도시락 | RESTAURANT |
| 판매자 | 정다은 (목감우리반찬) | 목감 우리반찬 | GROCERY |

각 매장에는 시흥시 권역 주소 · 좌표, 전화번호, 평점, 메뉴 1개, 오늘 판매 가능한 마감할인 상품 1개가 함께 생성됩니다.

---

## 도메인 참고

### 주문 상태 흐름

```
PENDING ──▶ PREPARING ──▶ READY ──▶ COMPLETED
   │              │          │
   └──────────────┴──────────┴──▶ CANCELLED
```

### 매장 카테고리

```
BAKERY  /  CAFE  /  RESTAURANT  /  GROCERY  /  OTHER
```

### 개발 환경 기본값

| 항목 | 값 |
| --- | --- |
| 백엔드 주소 | `http://localhost:8080` |
| 에뮬레이터 백엔드 주소 | `http://10.0.2.2:8080/` |
| API 문서 (Swagger) | `http://localhost:8080/swagger-ui/index.html` |
| H2 콘솔 | `http://localhost:8080/h2-console` |
| Access Token 만료 | 30분 |
| Refresh Token 만료 | 14일 |
