# 📊 Hotel Booking Demand Analysis

> 목적: 호텔 예약 데이터 분석을 통해 예약 취소에 영향을 미치는 요인을 파악하고, 호텔 운영자가 취소율을 낮추기 위한 전략을 수립

---

## 📁 데이터셋 개요

- **출처**: [Kaggle 포르투갈의 City Hotel과 Resort Hotel 예약 데이터](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)
- **기간**: 2015.07.01 ~ 2017.08.31
- **특징**: 예약 상태, 숙박 정보, 예약 경로, 고객 정보, 과거 예약 이력 등을 포함

---

## 🎯 분석 목표

1. 예약 취소에 영향을 주는 요소 파악
2. 취소율이 높은 고객/조건 탐색
3. 호텔 운영 전략 개선 아이디어 도출

---

## 🛠️ 사용 기술

- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Jupyter Notebook

---

## 🔍 분석 요약

### 1. 데이터 전처리
- `adults`, `children`, `babies` 수 가 모두 0인 데이터 제거
- `is_repeated_guest`와 과거 예약 이력 모순 제거
- 성인이 없는 예약 + 주차 요구 → 비정상으로 간주해 제거

### 2. 호텔 유형별 비교
- City Hotel의 예약 취소율이 Resort Hotel보다 높음
- City Hotel은 단기 숙박 위주, Resort Hotel은 장기 숙박 위주
- 여름철에는 전체 고객 수가 증가, 겨울철에는 감소

### 3. 주요 변수와 예약 취소 간의 관계

| 변수 | 인사이트 |
|------|----------|
| `lead_time` | 30일 이상 대기일 → 취소율 ↑|
| `country` | 특정 국가(동남아시아, 아랍권 등) → 취소율 ↑ |
| `market_segment` | Direct 예약보다 Agent/Company 경유 시 취소율 ↑ |
| `total_of_special_requests` | 추가 요청이 많을수록 예약 취소율 ↓ |
| `adults` | 성인 5명 이상 → 취소율 ↑ |
| `previous_cancellations` | 과거 취소 이력 → 현재 취소율 ↑ |

---

## 💡 예약 취소율 개선 아이디어

1. **City Hotel 집중 관리**
   - 예약 취소율이 더 높은 **City Hotel 관리에 집중**

2. **대기일 기반 조치**
   - 대기일이 30일 이상아면 **보증금 요구 및 리마인드 메시지 발송**

3. **국가 맞춤 전략**
   - 취소율 높은 국가 고객에 대해 **주의 모니터링 또는 특화 서비스 제공**

4. **중간 대행 업체 점검**
   - Agent/Company을 통한 예약은 **2차 확인 필요**
   - 호텔 자체 프로모션 제공을 통한 **Direct 예약 유도**

5. **단체 고객 전략**
   - 성인 5명 이상 고객 대상 **전용 패키지 또는 이벤트 룸 제공**

6. **과거 취소 고객 필터링**
   - 반복 취소 이력 고객에게 **보증금 부과 또는 제한 조건 설정**

---

## 📂 프로젝트 구조

```bash
├── data/
│   └── hotel_bookings.csv
├── notebook/
│   └── hotel_data_analysis.ipynb
├── README.md
