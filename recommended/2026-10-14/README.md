# 논문 추천 2026-10-14

> 이 추천은 의사의 검토가 필요합니다. 자동 선별 결과이며 임상 판단을 대신하지 않습니다.

- **연구 날짜**: 2026-10-14 (Asia/Seoul 기준 어제)
- **실제 검색 기간**: 2026-09-15 ~ 2026-10-14 (당일 창은 결과 없음, 7일 창은 3편, 약 30일 창은 10편이었으나 기준을 만족한 논문은 1편뿐이라 관련성 기준을 낮추지 않고 1편만 추천)
- **검색어**: `chest radiograph deep learning`

## 코호트 요약 (집계 수치만)

- 흉부 X선 272건, 연령 9~87세(평균 약 51.5세), 라벨 조합 48종
- 촬영 PA 184 / AP 88, 성별 남 136 / 여 136
- 정상 145건(53.3%), 이상 127건; 침윤 21, 무기폐 16, 결절 7, 섬유화 6, 흉수 6 등 단일 라벨 소수 클래스 다수

## 추천 논문

### 1. Performance uncertainty in medical image analysis: a large-scale investigation of confidence intervals
[DOI](https://doi.org/10.1016/j.media.2026.104349) · Medical Image Analysis · 축: 성능 불확실성, 소규모 코호트 평가
- **왜 관련 있나**: 24개 과제에 걸쳐 CI 신뢰성이 표본 수·지표·집계 방식(macro vs micro)에 따라 크게 달라짐을 보이고 결정 트리를 제시합니다.
- **우리 데이터 근거**: 272건 중 결절 7, 섬유화 6처럼 이상 소견 클래스가 매우 작아 클래스별 성능 추정의 불확실성이 큽니다.
- **알 수 없는 것**: 방법론 연구라 임상 코호트 결과가 없고, 우리 데이터로 결론을 검증할 수 없습니다.

## 제외한 후보

- Repurposing adult AI radiograph models for neonatal care (Nature Biomedical Engineering): 신생아 대상이며 우리 코호트(9세 이상)와 맞지 않음.
- Artificial intelligence for opportunistic osteoporosis screening on chest radiographs, Physician involvement and research quality in chest X-ray foundation models, Staged purpose-blinded evaluation… (npj Digital Medicine), On-premise medical AI agents (Nature Medicine): 기존 `recommended/`와 중복.
- AI-assisted scoping review of code sharing (Nature Medicine), digital twin 의학교육 리뷰, CT 비전-언어 모델, 광자계수 CT 저선량 연구: 흉부 X선 코호트와 직접 관련 없음.

모든 추천은 의사의 검토가 필요합니다.
