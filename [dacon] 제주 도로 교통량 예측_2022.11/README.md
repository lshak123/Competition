# 제주 도로 교통량 예측

<br/>

## 프로젝트 기간
- 2022.10~2022.11

<br/>

## 프로젝트 소개
- 제주도내 주민등록인구는 매년 증가하고 있으며, 외국인 관광객까지 고려하면 상주인구가 90만명을 넘을 것으로 추정
- 제주도민 증가와 외국인의 증가로 현재 제주도의 교통체증이 심각한 문제로 떠오르고 있다.
- 따라서 제주도 도로 교통량 예측 AI 알고리즘 개발을 주제로 프로젝트를 진행
- 평가지표 : ROC-AUC

<br/>

## 프로젝트 과정

<br/>

#### 1. Data Processing
- 특정 범주의 빈도가 대부분인 경우 제거
- 주어진 데이터는 제주도 지역의 경도 위도가 제공된 데이터로 시작지점 목적지점이 나뉜 데이터이다.
- 따라서 node name을 labeling하고 출발, 도착지점의 방향을 고려한 labeling을 시도, 위도 경도를 통한 거리와 방위각을 계산하여 feature로 추가했다.
- 추가적으로 달, 요일 요소가 중요하다고 여겨져 해당 feature를 만들어 주었고, 몇몇 변수에 대해 target encoding을 진행, 나머지 범주형 변수에 대해 label encoding을 진행했다.
- 
#### 2. Modeling
- LGBM과 CatBoost 모델을 bayesian optimization 활용하여 튜닝하였고, submission을 생성해 최종적인 submission을 생성했다.
- 추가로 정형 데이터를 위한 딥러닝 모델인 TabNet을 사용하였다. TabNet 또한 bayesian optimization을 통한 튜닝을 진행하였고, submission을 생성했다.

#### 3. Ensemble
- 이렇게 얻은 submission들의 가중평균 ensemble을 통해 최종 결과물을 도출했다


## 느낀점
제주 도로 교통량 예측 프로젝트를 진행하면서 이전 공모전의 Data Leakage로 인한 실격을 인지하고 해당 부분에 대해 더욱 꼼꼼하게 확인하며 프로젝트를 진행하였으며,
time series 데이터의 예측은 예측과 가까운 기간이 더욱 예측에 도움을 줄 수 있다는 것을 다시 한번 인지하게됐다.


![image](https://user-images.githubusercontent.com/97331900/217137968-6221aaa0-4193-4a6c-a059-8971862f7301.png)
