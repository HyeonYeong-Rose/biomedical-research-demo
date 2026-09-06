# 일일 논문 추천 — 2026-09-05

## 검색 개요
- **연구 기준일**: 2026-09-05 (요청된 `REQUESTED_DATE` 없음 → Asia/Seoul 기준 어제 날짜 사용)
- **실제 검색 창**: 당일(2026-09-05~2026-09-05) 및 7일(2026-08-30~2026-09-05) 창에서는 결과가 없어, 30일 창(2026-08-06~2026-09-05)까지 넓혀 검색함
- **검색 쿼리**: `chest radiograph deep learning external validation generalization` (1차), 보강 검색으로 `chest X-ray multi-label classification reader study clinical validation`, `chest X-ray radiologist AI reader study external cohort` 사용
- 일부 방법론 학회(MICCAI, IPMI, CVPR, NeurIPS, ICLR)는 반복 호출 중 429 오류로 응답을 받지 못했으나, 저널 소스(OpenAlex)에서는 충분한 후보를 확보함

## 코호트 개요 (환자 단위 값 없음, 집계치만)
- 총 272건 영상, 152명 환자 (`llm.hospital` 마스킹 뷰 기준)
- 성별: 남 136 / 여 136 (균형)
- 연령: 9–87세, 평균 51.5세
- 촬영 자세: PA 184건, AP 88건
- 기관: INST01(62), INST02(56), INST03(54), INST05(52), INST04(48) — 5개 기관 분포
- 소견 분포: No Finding 145건(53%)이 가장 많고, Infiltration(21), Atelectasis(16), Nodule(7), Fibrosis(6), Effusion(6), Cardiomegaly(5), Pneumothorax(5) 등 나머지 소견은 소수 사례에 국한된 뚜렷한 클래스 불균형이 있음

## 선정 축 (Axes)
1. **기관 간 일반화** — 여러 기관/외부 코호트에서의 성능 재현성을 다루는 논문
2. **저빈도 소견의 롱테일 문제** — 흔치 않은 진단·소견에서의 성능 저하를 다루는 논문
3. **AI 보조 판독 성능** — 방사선의 판독 정확도·속도에 대한 AI 보조 효과를 정량화한 논문

## 추천 논문

### 1. Advancing human-centric AI for robust X-ray analysis through holistic self-supervised learning (RayDINO)
- **축**: 기관 간 일반화, 인구통계학적 편향
- **왜 관련 있는가**: 84만 장으로 학습, 12개 외부 데이터셋 8.2만 장으로 검증한 자기지도 흉부 X-ray 파운데이션 모델. 연령·성별 편향을 정량 분석한 점이 우리 코호트의 넓은 연령 분포(9–87세)와 균형 잡힌 성비(136/136)에 직접 대응됨.
- **한계**: 우리 코호트는 272건 규모로 논문의 8.2만 장 검증 규모에 비할 통계적 검정력이 없음.
- 출처: https://doi.org/10.1038/s41467-026-76076-4

### 2. Multicenter evaluation of four large language models for automated spine imaging diagnosis
- **축**: 기관 간 일반화, 저빈도 소견의 롱테일 문제
- **왜 관련 있는가**: 3개 기관 2만여 건의 판독문으로 4개 LLM을 비교, 저빈도 소견에서 정밀도가 19–42%p 하락하는 롱테일 문제를 정량 보고. 우리 코호트에서도 No Finding(53%) 대비 Nodule(7건), Fibrosis(6건) 등 극단적 불균형이 존재해 동일한 위험 구조를 공유함.
- **한계**: 대상 장기(척추)와 입력 형태(텍스트 판독문)가 우리 흉부 영상 코호트와 달라 정밀도 하락 폭을 그대로 대입할 수 없음.
- 출처: https://doi.org/10.1038/s41746-026-03133-z

### 3. A foundation model for acute abdomen diagnosis stratification and triage on noncontrast computed tomography (AbdomenNet)
- **축**: 기관 간 일반화, AI 보조 판독 성능
- **왜 관련 있는가**: 3개 외부 기관, 2528명 코호트에서 다독자 교차 연구로 AI 보조 시 방사선의 AUROC가 0.812→0.924로 개선됨을 보고. 우리 코호트도 5개 기관에 걸친 다기관 구성이라 유사한 교차검증 설계를 참고할 수 있음.
- **한계**: 대상 모달리티(복부 NCCT)와 질환군이 우리의 흉부 X-ray 코호트와 달라 보고된 AUROC 개선치를 직접 적용할 수 없음.
- 출처: https://doi.org/10.1038/s41467-026-76634-w

## 참고 사항
- 본 추천은 자동 검색·집계 결과이며, 실제 임상 적용 여부는 반드시 담당 의료진의 검토를 거쳐야 합니다.
- 환자 단위 데이터는 어떤 형태로도 포함하지 않았으며, 모든 수치는 코호트 수준 집계치입니다.
