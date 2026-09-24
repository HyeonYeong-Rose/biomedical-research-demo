# 2026-09-23 논문 추천

- **연구 기준일**: 2026-09-23 (Asia/Seoul 기준 어제)
- **실제 검색 창**: 2026-09-23 단일일(0건) → 2026-09-17~2026-09-23 7일(관련 없는 1건) → 2026-08-24~2026-09-23 30일(채택)
- **검색 질의**: `chest radiograph deep learning diagnosis` (기본), 보조 질의로 `synthetic medical imaging generative model validation`, `multi-institutional external validation chest X-ray AI` 등을 함께 사용해 교차 확인

## 코호트 요약 (집계 수준만 표기)

- 총 272건의 스터디, 153명의 환자(고유 `patient_key` 기준)
- 성별: 남 136 / 여 136, 평균 연령 남 48.7세 / 여 54.3세
- 소견 분포: No Finding 145건, Infiltration 21건, Atelectasis 16건, Nodule 7건, Effusion 6건, Fibrosis 6건, Pneumothorax 5건, Cardiomegaly 5건 등 다수의 저빈도 소견이 혼재
- 촬영 자세: PA 184건, AP 88건
- 영상 크기: 가로 1773–3056px, 세로 1835–3056px
- 기관 코드: INST01(62) > INST02(56) > INST03(54) > INST05(52) > INST04(48) 로 5개 기관에 비교적 고르게 분산
- 판독 상태: final 76, addendum 70, preliminary 68, amended 58
- **전체 272건이 `is_synthetic = true`로 표시된 합성 데이터**임을 확인

## 채택 논문

### 1. Staged purpose-blinded evaluation of provenance risk from a general-purpose generator in breast ultrasound
- npj Digital Medicine, 2026-09-19
- **왜 관련 있는가**: 우리 코호트 전량이 합성 영상이라는 점에서, 판독자가 출처를 모른 채 소견을 신뢰할 위험을 다룬 이 논문의 문제의식이 그대로 적용된다. 사전 정보 없이 12명 판독자 중 3명만 자발적으로 출처를 의심했다는 결과는 우리 데이터의 임상 활용 전 반드시 검토해야 할 지점을 시사한다.
- **우리 데이터가 뒷받침하는 것**: 5개 기관, 다양한 소견 분포를 가진 272건 전량이 합성이라는 사실 자체가 이 논문이 지적하는 시나리오와 구조적으로 유사하다.
- **확인해 줄 수 없는 것**: 원 논문은 유방 초음파 단일 생성기 사례이며, 흉부 X-ray에서의 판독 정확도나 출처 검출률은 별도로 검증해야 한다.
- 링크: https://doi.org/10.1038/s41746-026-03209-w

### 2. Benchmarking AI-generated thin-slice CT under clinical reconstruction conditions: a multicohort study
- npj Digital Medicine, 2026-09-16
- **왜 관련 있는가**: 여러 기관·장비 조건에서 합성/재구성 영상이 실제 촬영 조건과 어긋나는 정도를 정량화하는 접근으로, 우리 코호트처럼 5개 기관 코드에 걸쳐 영상 크기와 특성이 흩어져 있는 데이터의 품질 점검 방법론으로 참고할 수 있다.
- **우리 데이터가 뒷받침하는 것**: img_width/img_height가 1773–3056px 범위로 넓게 분포하고 기관 코드별 표본 수가 48~62건으로 상이해, 기관별 영상 특성 이질성을 점검할 필요가 있다.
- **확인해 줄 수 없는 것**: CT 슬라이스 두께 합성에 국한된 연구로, 흉부 X-ray의 해상도·자세(AP/PA) 문제에 대한 직접적 검증은 아니다.
- 링크: https://doi.org/10.1038/s41746-026-03253-6

### 3. Conditional deep generative modeling of blood-based infrared spectra enables controlled in-silico phenotyping studies
- npj Digital Medicine, 2026-09-17
- **왜 관련 있는가**: 연령·성별 등 조건을 지정한 합성 데이터로 희소 하위집단을 보강하는 방법론으로, 우리 코호트의 Nodule(7건), Pneumothorax(5건) 같은 저빈도 소견 보강 전략을 고민할 때 참고할 수 있다.
- **우리 데이터가 뒷받침하는 것**: 성별은 남녀 각 136명으로 균형이나 평균 연령 차(48.7세 vs 54.3세)가 있고, 다수 소견이 한 자릿수 건수에 그쳐 조건부 생성으로 보강할 여지가 있는 구조다.
- **확인해 줄 수 없는 것**: 표 형태의 혈액 스펙트럼 신호를 다룬 연구로, 흉부 X-ray의 공간적 병변 패턴 합성·검증에 동일 방법이 통할지는 별도 확인이 필요하다.
- 링크: https://doi.org/10.1038/s41746-026-03226-9

## 비교 축 (axes)

- **합성 데이터 신뢰성**: 판독자가 합성 영상을 신뢰하거나 오인할 위험, 조건부 생성이 실제 분포를 얼마나 충실히 재현하는지
- **영상 재구성 품질**: 기관/장비 간 영상 특성 차이가 재구성 또는 합성 품질에 미치는 영향
- **코호트 불균형**: 희소 소견/하위집단을 합성 데이터로 보강하는 전략

## 주의

이 추천은 자동화된 검색·집계 결과이며, 실제 임상 적용 여부는 반드시 담당 의료진의 검토를 거쳐야 합니다.
