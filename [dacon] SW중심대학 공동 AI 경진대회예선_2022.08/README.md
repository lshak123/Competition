# 심리 성향을 예측 프로젝트

<br/>

## 프로젝트 기간
- 2021.08

<br/>

## 프로젝트 소개
 심리학 테스트 데이터를 분석하여 "심리 성향을 예측"하는 알고리즘을 개발합니다.<br/>
 평가지표 : ROC-AUC
 
<br/>

#### 1. 데이터 시각화 및 전처리
- 각 테스트에 대한 답변을 시각화 하여 이상치를 처리하고 Null값에 대해 전처리를 진행시킴
- target data의 편향이 있어 Oversampling(SMOTE, BorderlineSMOTE)를 활용하여 target값의 데이터 비율을 맞춰줌

<br/>

#### 2. Modeling
- 팀원끼리 모델을 나눠 ExtraTree, LGBM등의 모델을 학습
- bayBayesian Optimization을 활용하여 파라미터 튜닝을 진행했다.
 
 <br/>
 
 #### 3. Ensemble
 - 최종적으로 나온 submission들에 대해 submission간의 상관관계를 확인 후 앙상블을 통해 최종 submission을 생성.

## 느낀점
public 0.90684(5위), private 0.90276(7위)으로 높은 성과를 이뤘으나, 
Train Data의 결측치를 처리할 때 Test Data의 통계값을 이용하여 Data Leakage로 인해 실격이 되었다.
상당히 아쉬웠지만 이 대회를 통해 Data Leakage에 대해 더욱 꼼꼼히 신경쓰게됐고, 다시는 이런 실수를 하지 않도록 철저하게 검토할것입니다.<br/><br/>
![image](https://user-images.githubusercontent.com/97331900/216994989-52635eec-04f5-4fbe-9b55-9ab2ecafd339.png)

