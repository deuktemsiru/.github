<h1 align="center">득템시루 🍱</h1>

<p align="center">
  <b>마감 임박 할인 상품을 발견하고, 픽업으로 득템하세요</b><br/>
  구매자와 판매자를 실시간으로 연결하는 마감 할인 픽업 예약 서비스
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"/>
  <img src="https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white"/>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white"/>
</p>

---

## 프로젝트 소개

> **"오늘 팔리지 않으면 버려지는 것들이 있습니다."**

베이커리의 마감 빵, 카페의 남은 샌드위치, 반찬 가게의 당일 반찬 — 매일 폐기되는 음식은 생각보다 훨씬 많습니다. **득템시루**는 마감 임박 상품이 헐값에 버려지는 문제를 해결하기 위해 기획한 서비스입니다.

구매자는 주변 할인 매장을 지도에서 찾아 바로 픽업 예약을 하고, 판매자는 남은 재고를 효율적으로 소진하면서 매출도 올릴 수 있습니다. 구매자 앱, 판매자 앱, Spring Boot 백엔드 세 가지 프로젝트로 구성된 풀스택 서비스입니다.

---

## 팀원 소개

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
      <sub>백엔드 · Android · AWS</sub><br/>
      <sub>백엔드 API 개발</sub><br/>
      <sub>구매자·판매자 앱 개발</sub><br/>
      <sub>AWS 배포</sub><br/>
    </td>
    <td align="center">
      <a href="https://github.com/ken-jeong">
        <img src="https://github.com/ken-jeong.png" width="100px" alt="정상겸"/><br/>
        <b>정상겸</b>
      </a><br/>
      <sub>기획 · 백엔드 · Android</sub><br/>
      <sub>백엔드 설계·구현</sub><br/>
      <sub>구매자·판매자 앱 개발</sub><br/>
      <sub>모니터링 구성</sub>
    </td>
    <td align="center">
      <a href="https://github.com/Asterisk0707">
        <img src="https://github.com/Asterisk0707.png" width="100px" alt="한동혁"/><br/>
        <b>한동혁</b>
      </a><br/>
      <sub>Android · 백엔드 · 발표</sub><br/>
      <sub>구매자 앱 개발</sub><br/>
      <sub>엔티티 설계·알림 API</sub><br/>
      <sub>최종 발표</sub>
    </td>
    <td align="center">
      <a href="https://github.com/Ra-seungmin">
        <img src="https://github.com/Ra-seungmin.png" width="100px" alt="라승민"/><br/>
        <b>라승민</b>
      </a><br/>
    </td>
  </tr>
</table>

---

## 화면 구성

| 구매자 앱 | 판매자 앱 |
| --- | --- |
| 홈 · 카테고리 탐색 | 홈 대시보드 |
| 지도 · 경로 안내 | 메뉴 · 상품 등록 |
| 매장 상세 · 장바구니 | 주문 관리 · 픽업 검증 |
| 주문 · 픽업 확인 | 매출 분석 · 정산 |

> 스크린샷은 추후 추가 예정입니다.

---

## Repository 구성

| Repository | 설명 |
| --- | --- |
| [`deuktemsiru_buyer`](https://github.com/deuktemsiru/deuktemsiru_buyer) | 매장 탐색 · 지도 · 경로 안내 · 장바구니 · 주문 · 찜 · 마이페이지 Android 앱 |
| [`deuktemsiru_seller`](https://github.com/deuktemsiru/deuktemsiru_seller) | 홈 대시보드 · 메뉴·상품 관리 · 주문 처리 · 픽업 검증 · 매출 분석 Android 앱 |
| [`deuktemsiru_backend`](https://github.com/deuktemsiru/deuktemsiru_backend) | 카카오 인증 · JWT · 매장 · 주문 · 정산 · 모니터링 Spring Boot 백엔드 |

---

## 기술 스택

### Backend

<p>
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white"/>
  <img src="https://img.shields.io/badge/Java 21-ED8B00?style=flat-square&logo=openjdk&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring Boot 4-6DB33F?style=flat-square&logo=springboot&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white"/>
  <img src="https://img.shields.io/badge/JPA / Hibernate-59666C?style=flat-square&logo=hibernate&logoColor=white"/>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/H2-004088?style=flat-square&logo=h2&logoColor=white"/>
  <img src="https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white"/>
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white"/>
  <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
</p>

### Android (공통)

<p>
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white"/>
  <img src="https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white"/>
  <img src="https://img.shields.io/badge/Retrofit 2-48B983?style=flat-square&logo=square&logoColor=white"/>
  <img src="https://img.shields.io/badge/Coroutines-7F52FF?style=flat-square&logo=kotlin&logoColor=white"/>
  <img src="https://img.shields.io/badge/Kakao SDK-FFCD00?style=flat-square&logo=kakao&logoColor=black"/>
  <img src="https://img.shields.io/badge/Material Design-757575?style=flat-square&logo=materialdesign&logoColor=white"/>
</p>

### 구매자 앱 추가

<p>
  <img src="https://img.shields.io/badge/Google Maps SDK-4285F4?style=flat-square&logo=googlemaps&logoColor=white"/>
  <img src="https://img.shields.io/badge/Tmap API-1428A0?style=flat-square&logoColor=white"/>
  <img src="https://img.shields.io/badge/Navigation Component-3DDC84?style=flat-square&logo=android&logoColor=white"/>
</p>

### 판매자 앱 추가

<p>
  <img src="https://img.shields.io/badge/ZXing (QR)-000000?style=flat-square&logoColor=white"/>
  <img src="https://img.shields.io/badge/Flexbox Layout-3DDC84?style=flat-square&logo=android&logoColor=white"/>
</p>

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

두 앱은 카카오 SDK로 로그인한 뒤 백엔드로부터 JWT를 발급받습니다. 이후 모든 요청은 OkHttp Interceptor를 통해 `Authorization: Bearer {accessToken}` 헤더를 자동으로 첨부합니다. 토큰 만료 시 Refresh Token으로 자동 갱신합니다.

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

### 판매자 앱

| 기능 | 설명 |
| --- | --- |
| 홈 대시보드 | 매장 운영 상태, 오늘 매출, 주문 현황, 활성 판매 상품 수 |
| 메뉴 등록 | 단계별 입력 — 이름 · 가격 · 할인율 · 수량 · 픽업 시간 · 알레르기 · 이미지 |
| 판매 상품 관리 | 등록 메뉴 기반 당일 판매 상품 생성, 상태 변경, 삭제 |
| 주문 관리 | 신규 → 준비 중 → 픽업 대기 → 완료 탭 전환, 주문 상세 바텀시트 |
| 픽업 검증 | QR 스캔 또는 코드 직접 입력으로 픽업 완료 처리 |
| 매출 분석 | 주간 / 월간 / 연간 Bar · Pie 차트, 인기 메뉴 순위 |
| 고객 알림 | 반경 내 구매자에게 알림 발송 · 발송 내역 조회 |
| 정산 | 월별 정산 내역 확인 · 출금 신청 |

### 백엔드

| 기능 | 설명 |
| --- | --- |
| 카카오 인증 / JWT | Access Token 기반 로그인·자동 회원가입, JWT 발급·갱신 |
| 매장 / 찜 / 장바구니 | 카테고리별 매장 목록, 찜 등록·해제, 서버 사이드 장바구니 |
| 주문 | 주문 생성·조회·취소, 판매자 주문 상태 변경 |
| 판매자 관리 | 메뉴·상품 CRUD, 픽업 코드 검증, 매출 통계, 정산·출금 |
| 모니터링 | Prometheus + Grafana — HTTP · DB · JVM · 비즈니스 메트릭 |

---

## 시작하기

### 1. 백엔드 실행

```bash
cd deuktemsiru_backend
export JAVA_HOME="/Applications/Android Studio.app/Contents/jbr/Contents/Home"
./gradlew bootRun
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

### 3. 앱 실행

Android Studio에서 `deuktemsiru_buyer` 또는 `deuktemsiru_seller`를 열고 `app`을 실행합니다.

에뮬레이터에서 로컬 백엔드에 접속할 때는 `http://10.0.2.2:8080/`을 사용합니다.
실기기나 원격 서버에 연결하려면 `local.properties`에 아래 항목을 추가합니다.

```properties
BACKEND_BASE_URL=http://your-backend-host:8080/
```

---

## 샘플 데이터

백엔드 최초 실행 시 H2 DB가 비어 있으면 시흥시 생활권 기반 샘플 데이터가 자동 생성됩니다.

| 역할 | 이름 | 매장 | 카테고리 |
| --- | --- | --- | --- |
| 구매자 | 홍길동 | — | — |
| 판매자 | 김영희 | 오이도 굽는집 | BAKERY |
| 판매자 | 박민준 | 배곧 로스터리 | CAFE |
| 판매자 | 이수진 | 정왕시장 분식 | RESTAURANT |
| 판매자 | 최하늘 | 은행동 찬찬도시락 | RESTAURANT |
| 판매자 | 정다은 | 목감 우리반찬 | GROCERY |

---

## 도메인 참고

**주문 상태 흐름**

```
PENDING ──▶ PREPARING ──▶ READY ──▶ COMPLETED
   │              │          │
   └──────────────┴──────────┴──▶ CANCELLED
```

**매장 카테고리** — `BAKERY` / `CAFE` / `RESTAURANT` / `GROCERY` / `OTHER`

**개발 환경 기본값**

| 항목 | 값 |
| --- | --- |
| 백엔드 주소 | `http://localhost:8080` |
| 에뮬레이터 백엔드 주소 | `http://10.0.2.2:8080/` |
| Swagger API 문서 | `http://localhost:8080/swagger-ui/index.html` |
| H2 콘솔 | `http://localhost:8080/h2-console` |
| Access Token 만료 | 30분 |
| Refresh Token 만료 | 14일 |
