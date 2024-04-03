# Upstage AI Lab 2기 ML Competition 3조 Report

## Team

| ![이승현](https://avatars.githubusercontent.com/u/66935871?v=4) | ![한민규](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/imgs/MangooH.png) | ![박언선](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/imgs/eonseon.png) | ![이광우](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/imgs/kwangwoo.png) | ![정혜윤](https://avatars.githubusercontent.com/u/118159352?v=4) |
| :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: |
|            [이승현](https://github.com/EffortLEE1008)             |            [한민규](https://github.com/MangooH)             |            [박언선](https://github.com/eonpark)             |            [이광우](https://github.com/UpstageAILab)             |            [정혜윤](https://github.com/Hye-yoonJeong)             |
|                            팀장, 이상치 탐색                             |                            Baseline 구축, Feature Engineering, Modeling                             |                            담당 역할                             |                            담당 역할                             |                            담당 역할                             |

## 1. Competiton Info

### Overview

- House Price Prediction of Seoul apartments
- Task : Regression

### Timeline

- March 20, 2024 - Start Date
- April 2, 2024 - Final submission deadline (1pm)

### Evaluation

- RMSE

## 2. Components

### Directory

- _Insert your directory structure_

## 3. Data descrption

### Dataset overview

- Given Dataset : 국토교통부 실거래가, 서울시 공공주택 아파트 정보
- Train Data : 2007-01-01 ~ 2023-06-30, size (1188822, 52)
- Test Data : 2023-07-01 ~ 2023-09-26, size (9272, 51)

### EDA

- 구별, 동별 실거래가 평균
![구별평균가](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/yoon/plots/%EA%B5%AC%EB%B3%84%ED%8F%89%EA%B7%A0%EA%B0%80.png)
![동별평균가](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/yoon/plots/%EB%8F%99%EB%B3%84%ED%8F%89%EA%B7%A0%EA%B0%80.png)
- 구별, 동별 실거래가 분포
![구별실거래가분포](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/imgs/%EC%9E%90%EC%B9%98%EA%B5%AC%EB%B3%84%EA%B0%80%EA%B2%A9%EB%B6%84%ED%8F%AC.png)
![동별실거래가분포](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/imgs/%EB%8F%99%EB%B3%84%EA%B0%80%EA%B2%A9%EB%B6%84%ED%8F%AC.png)


### Feature engineering

- 계약년도와 건축년도 차이에 따른 실거래가 평균
yrs_diff = 계약년도 - 건축년도
![yrs_diff](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/imgs/yrs_diff.png)
- 구나 동에 대한 정보를 단순 명목형 변수가 아닌 ordinal 변수라고 판단하여 단순하게 label encoding을 적용하기 보다는 평균가의 순서로 encoding함

## 4. Modeling

### Model description

- 개별적으로 XGBoost와 LGBM에 대해 테스트해 본 후 베이스라인은 LGBM으로 통일
- Dataset Split 방식은 Hold out random, Hold out time split, Time series split 등을 시도


### Modeling Process

- _Write model train and test process with capture_

## 5. Result

### Leader Board

- Public LB
![publicLB](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/imgs/publicLB.png)
- Private LB
![privateLB](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/imgs/privateLB.png)
- 1st in Public LB 14691.1409 → 3rd in Private LB 12614.1573

### Presentation

- [[패스트캠퍼스] Upstage AI Lab 2기_그룹 스터디_3조_ML대회_final.pdf ](https://github.com/UpstageAILab2/upstage-ml-regression-3/blob/main/docs/pdf/%5B%ED%8C%A8%EC%8A%A4%ED%8A%B8%EC%BA%A0%ED%8D%BC%EC%8A%A4%5D%20Upstage%20AI%20Lab%202%EA%B8%B0_%EA%B7%B8%EB%A3%B9%20%EC%8A%A4%ED%84%B0%EB%94%94_3%EC%A1%B0_ML%EB%8C%80%ED%9A%8C_final.pdf)

## etc

### Meeting Log

- [Meeting log](https://www.notion.so/f6317c9bc94c436db7c85008be72feb7?v=35c93e65be114867af23a0365ff9e1a0)

### Reference

- [배성완, & 유정석. (2018). 기계 학습을 이용한 공동주택가격 추정: 서울 강남구를 사례로.](http://www.kreaa.or.kr/data/vol24-1/24_01_05.pdf)

