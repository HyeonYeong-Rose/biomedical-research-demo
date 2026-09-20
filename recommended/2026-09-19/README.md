# 일일 논문 추천 — 2026-09-19

## 검색 정보

- **연구 기준일**: 2026-09-19 (요청된 날짜 없음 → Asia/Seoul 기준 어제)
- **실제 검색 창**: 최초 1일(2026-09-19) → 7일(2026-09-13~09-19) 창에서 결과 없음 →
  30일 창(2026-08-20~2026-09-19)으로 확대하여 최종 검토
- **검색 쿼리**: 아래 코호트 특성을 반영해 직접 작성한 쿼리를 사용했습니다.
  - `chest X-ray multi-label diagnosis deep learning`
  - `chest radiograph AI diagnostic accuracy`
  - `on-premise medical AI agent reliability` (30일 창에서 추가 확인)
  - `pulmonary nodule chest CT artificial intelligence radiologist`
  - MICCAI/IPMI/CVPR/NeurIPS/ICLR(arXiv 경유)은 이번 검색 창에서 모두 접근 오류
    (HTTP 406/429)로 결과를 받지 못했으며, Nature 계열/Radiology 계열 저널
    (OpenAlex 경유)에서만 결과를 확인했습니다.

## 코호트 요약 (환자 단위 값 없음)

- 총 272건의 흉부 X선 판독 기록, 고유 환자 153명 (모두 합성/`is_synthetic = true` 데이터)
- 성별: 남성 136건(평균 연령 48.7세), 여성 136건(평균 연령 54.3세)
- 촬영 자세: PA 184건, AP 88건
- 5개 기관(INST01~05)에 48~62건씩 비교적 고르게 분포, 9개 장비(DEV01~09)에는
  15~40건으로 다소 불균등하게 분포
- 소견 분포: No Finding 145건(53%)이 가장 많고, 이어서 Infiltration 21건,
  Atelectasis 16건, Nodule 7건, Fibrosis/Effusion/Cardiomegaly가 각 5~6건 수준.
  일부 증례는 Atelectasis+Effusion+Infiltration 등 2~4개 소견이 동시에 표기됨
- 영상 해상도 1773~3056px, 픽셀 간격 0.139~0.194mm로 기관/장비 간 촬영 조건 편차 존재

## 선정 기준(축)

1. **선택적 자동화/불확실성 추정** — AI가 스스로 판단 신뢰도를 매겨 저위험 증례만
   자동 처리하고 애매한 증례는 사람에게 넘기는 전략을 다루는가
2. **실제 임상 워크플로 효과** — 실제 판독 시간·업무 흐름에 미치는 영향을 정량적으로
   보고했는가
3. **영상-언어 모델 신뢰성** — 서술형/자유 응답 과제에서 영상-언어 모델의 실제
   임상 추론 능력을 검증했는가

## 추천 논문

### 1. On-premise medical AI agents for reliable clinical decision-making
(*Nature Medicine*, 2026) — 축: 선택적 자동화/불확실성 추정, 원내 배포/거버넌스

MIMIC-IV 기반 진단 과제에서 판독 일관성 지표로 전체 증례의 절반가량을 98.9%
정확도로 자율 처리할 수 있음을 보였습니다. 우리 코호트는 No Finding이 53%를
차지하고 나머지 소견은 저빈도로 분산되어 있어, 흔한 정상 소견은 자동 처리하고
드문 이상 소견은 판독의 검토로 넘기는 선택적 자동화 설계와 맞물립니다. 다만 이
논문은 텍스트 기반 진단 과제만 다루므로 영상 판독 자체의 신뢰도 추정 효과는
확인할 수 없습니다.

- 링크: https://doi.org/10.1038/s41591-026-04609-x

### 2. Impact of Commercial Artificial Intelligence on Radiologist Reading Time for Pulmonary Nodule Evaluation at Chest CT
(*Radiology*, 2026) — 축: 실제 임상 워크플로 효과, 저빈도 소견 검출

실제 임상 현장에서 상용 AI 결절 검출 도구 도입이 판독 시간을 줄였다는 실무
근거를 제공합니다. 우리 코호트에서 Nodule은 전체의 2.6%(7건)에 불과한 저빈도
소견이라 AI 보조가 판독 부담 경감에 실질적 도움이 될지 검토할 가치가 있습니다.
다만 대상 장비가 흉부 CT이고 우리 데이터는 흉부 단순 X선이라 동일한 시간 단축
효과가 재현될지는 우리 데이터로 확인할 수 없습니다.

- 링크: https://doi.org/10.1148/radiol.260484

### 3. The illusion of clinical reasoning: a benchmark reveals the pervasive gap in vision-language models for clinical competency
(*npj Digital Medicine*, 2026) — 축: 영상-언어 모델 신뢰성, 선택적 자동화/불확실성 추정

14개 영상-언어 모델을 정형외과 벤치마크로 평가한 결과, 객관식 문제(90%대
정확도)와 달리 서술형 영상 해석 과제에서는 정확도가 60%대로 급락했습니다.
우리 코호트는 다중 소견이 동시에 표기된 증례(예: Atelectasis+Effusion+Infiltration)를
포함하고 있어, 구조화된 분류를 넘어 서술형 판독 보조에 AI를 쓸 경우 유사한
성능 저하가 나타날 수 있는지 점검이 필요합니다. 다만 원 논문은 정형외과·
스포츠의학 영상 대상이라 흉부 X선에 그대로 일반화되는지는 확인할 수 없습니다.

- 링크: https://doi.org/10.1038/s41746-026-03191-3

## 검토 안내

위 추천은 자동 검색·요약 결과이며, 임상 적용 여부는 반드시 담당 의료진의
직접 검토를 거쳐야 합니다.
