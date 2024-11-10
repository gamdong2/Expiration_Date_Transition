# 만료 상태 변환일 예측 모델 개발

## Skills
<img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white"/>&nbsp; <!--scikit-learn-->
<img src="https://img.shields.io/badge/pandas-150458.svg?style=for-the-badge&logo=pandas&logoColor=white"/>&nbsp;  <!--pandas-->
<img src="https://img.shields.io/badge/numpy-4d77cf.svg?style=for-the-badge&logo=numpy&logoColor=white"/>&nbsp;  <!--numpy-->
<img src="https://img.shields.io/badge/Matplotlib-11557c.svg?style=for-the-badge&logo=Matplotlib&logoColor=white"/>&nbsp; <!--matplotlib-->

## 프로젝트 상세

- **진행 기간**: 2024년 8월 26일
- **프로젝트 유형**: 개인 프로젝트

## 프로젝트 목표
회원의 상태가 "만료"로 전환되는 시점을 예측하는 머신러닝 모델을 개발하여 고객 이탈을 사전에 방지할 수 있는 전략을 마련

## 사용한 데이터 셋
- **데이터**: 천재교육 서비스의 회원 활동 및 상태 변화 데이터(`만료상태변환일예측.csv`)
- **구성**: 회원의 활동 패턴 및 상태 전환 정보에 대한 데이터를 기반으로 머신러닝 회귀 모델을 학습

## 워크플로우

1. **패키지 임포트**
   - 사용한 주요 패키지: pandas, seaborn, numpy, matplotlib, scikit-learn, imblearn

2. **데이터 로드 및 요약**
   - 데이터를 로드하고 데이터프레임의 형태와 컬럼을 확인하여 데이터 구조를 파악

3. **데이터 전처리**
   - 결측값 처리 및 새로운 feature(`days_between_mean`, `days_between_slope`, `mcode_count`) 생성

4. **스케일링 및 변수 변환**
   - `MinMaxScaler`를 사용해 데이터를 0과 1 사이로 스케일링하고 로그 변환을 적용하여 데이터 분포를 정규화

5. **오버샘플링을 통한 클래스 불균형 해결**
   - SMOTE(Synthetic Minority Over-sampling Technique)를 사용하여 소수 클래스의 데이터를 증강

6. **모델 학습**
   - 선형 회귀 모델, 랜덤 포레스트 회귀 모델, 서포트 벡터 회귀(SVR) 모델을 학습하여 비교

7. **성능 평가 및 시각화**
   - RMSE, 학습 곡선, Residual Plot을 통해 각 모델의 성능을 평가하고 시각화하여 최적 모델 선정

## 프로젝트 결과

### 구현 기능
- 회원의 만료 상태 전환 시점을 예측할 수 있는 회귀 모델 구현
- 클래스 불균형 문제를 해결하고, 데이터 변환을 통해 모델 성능 최적화
- RMSE 및 학습 곡선을 통해 각 모델의 예측 성능을 분석하여 랜덤 포레스트 회귀 모델을 최적 모델로 선정

## 트러블 슈팅

- **오류**: "ValueError: cannot perform reduce with flexible type" - 데이터의 일부 열에 대한 연산이 불가능하여 발생한 오류
- **해결 방법**: 숫자형 데이터만 필터링하여 계산을 수행하도록 데이터 유형을 강제 변환하고, 비정상 값이 포함된 열을 제거하여 오류를 해결

## 프로젝트를 통해 얻은 역량

- 회귀 모델을 통한 시점 예측 및 데이터 전처리와 불균형 데이터 문제 해결
- 모델 성능 평가 및 지표 분석
- 다양한 지표를 통해 모델 성능을 비교 및 개선

