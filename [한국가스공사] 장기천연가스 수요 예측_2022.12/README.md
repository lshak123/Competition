# 장기천연가스 수요 예측

<br/>

## 프로젝트 기간
- 2022.09~2022.12

<br/>

## 프로젝트 소개
GDP, 업종별 부가가치, 인구통계 등을 활용해 천연가스의 수요량을 연단위로 예측하는 과제
<br/>학습 데이터 : 1996~2020년도의 GDP, 인구통계 및 천연가스 수요량<br/>
평가 데이터 : 2021~2034년도의 민수용 및 산업용 천연가스 수요량을 예측<br/>
예선 평가지표 : MAE<br/>
본선 평가지표 : MAPE<br/>

## 프로젝트 과정
#### 1. 도메인 조사 & 데이터 수집
천연가스 수요예측에 도움이 될 요소들에 대해 파악하기 위해 뉴스기사, 기존 연구 등을 조사해 제공된 데이터 이외에 외부데이터들을 수집하였다.
이후 EDA를 통해 데이터를 세가지 특징을 지닌 데이터로 분류하고 데이터활용방안을 제시했다.
<img src="https://user-images.githubusercontent.com/97331900/217025979-4bafc493-4f93-43c7-9d8e-f0d601409656.png"  width="1000" height="700">

<br/>

#### 2. Modeling
- 수집한 데이터들과 제공받은 데이터를 target에 대해 statsmodel에 적용하여 통계적으로 유의미한 feature들만 남기는 feature selection을 진행하였다.
- 이후 PCA, Polynomial기법등을 활용하여 feature engineering을 진행하였다.
- D-Linear라는 LSTF(Long Time Series Forecasting)과제에서 SOTA를 달성했던 모델을 활용하여 target값과 Feature들의 미래의 값을 예측했다.
- 예측된 Feature들을 활용해 선형모델과 ExtraTree모델을 사용하여 target값을 예측했다
<img src="https://user-images.githubusercontent.com/97331900/217025450-1b34f0cc-0411-4a2f-8576-720dbfdf50c0.png"  width="1000" height="700">

 <br/>
 
 #### 3. Ensemble
 - 최종적으로 D-Linear로 예측한 target, 여러개의 Feature들로 선형모델, ExtraTree모델을 활용하여 얻은 target값을 앙상블하여 최종 결과물을 얻었다.

## 느낀점
처음으로 로컬이 아닌 대회측에서 제공해준 가상서버에서 모델개발을 진행했다. 퍠쇄망 프로젝트라 라이브러리, git 활용과 같은 부분에서 어려움이 있었지만 대회측과의 소통을
통해 잘 해결했던거 같다.
- Time Series Forecasting task는 처음 접해보는 분야여서 좀 힘들었지만, 우리 팀이 구상한 방법론이 꽤나 좋게 적용하여 좋은 결과를 얻을 수 있었던 것 같다.<br/><br/>

<img src="https://user-images.githubusercontent.com/97331900/216931710-b9c0d9de-4c86-495c-bda2-7cfd7a3022ce.jpg"  width="500" height="700">
