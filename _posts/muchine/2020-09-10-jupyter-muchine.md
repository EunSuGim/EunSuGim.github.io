```title: "AI - pandas_practice"
title: "AI - muchine"
excerpt: "muchine"
toc: true
toc_sticky: true
categories: ai
tags: ai, muchine
last_modified_at: 2020-09-24T08:17:00-18:00
typora-root-url: ..\..\assets\img\muchine
```

## AI

간이 가지고 있는 학습능력, 응용력, 추론능력 컴퓨터를 통해서 
현하고자 하는 가장 포괄적인 개념입니다.
Machine Learning AI를 구현하는 하나의 방법론입니다. 
데이터를 이용해서 데이터의 특성과 패턴을 학습하고 그 결과를 바탕으로 
미지의 데이터에 대한 미래결과를 예측하는 프로그래밍 기법 중 하나입니다.



####  Machine Learning 방법들

Regression, SVM(Support Vector Machine), Random Forest, Descision Tree,
Neural Network(신경망), Clustering, Reinforcement Learning, 등등

Data Mining : 데이터간의 상관관계나 새로운 속성(featur)을 찾는것이 주 목적인 작업

Deep Learning : Machine Learning의 한 부분. Nerural network을 이용해서 
                             학습하는 알고리즘의 집합.(CNN, RNN, LSTM, GAN)

AI > Machine Learning > Deep Learning

Machine Learning은 Explicit program의 한계때문에 고안
Explicit program은 rule based program이라고 합니다.
이런 Explicit program을 이용하면 웬만한 프로그램은 전부 구현 가능
Explicit programming으로 할 수 없는 프로그램들이 있습니다.

- rule이 너무 많음, 조건이 너무 많음, 프로그램으로 표현하기 힘듬 등등



### MAchine Learning

프로그램 자체가 데이터를 기반으로 학습을 통해 배우는 능력을 가지는 프로그램

 - 지도학습(Supervised Learning)

 - 비지도학습(Unsupervised Learning)

 - 준지도학습(SemiSupervised Learning)

 - 강화학습(Reinforcement Learning)

   

 #### 지도학습(Supervised Learning)

학습에 사용되는 데이터와 그 정답(label)을 이용해서 데이터의 특성과 분포를 학습하고 미래결과를 예측하는 방법.

미래값 예측
Regression(회귀)
Classification(분류) - binary classification
multinomial classificaiton



#### 비지도학습(Unsupervised Learning)

학습에 사용되는 데이터가 label이 없는 데이터를 사용합니다.
정답(label)이 없는 데이터만을 이용하기 때문에 입력값 자체가 가지고 있는 특성과 분포를 이용해서
Grouping하는 Clustering(군집화)하는데 주로 사용합니다.



####  준지도학습 

지도학습 + 비지도학습

데이터의 일부분만 label이 제공되는 경우



#### 강화학습

Agent, Environment, Action, Reward 개념을 이용
게임쪽에서 많이 사용됨.

Supervised Learning(강화학습)
지도학습은 입력값(x)와 Label(t)를 포함하는 Training Data Set을 이용해서 
학습을 진행
학습된 결과를 바탕으로 => Predictive model을 만듬 => 미지의 데이터에 대해 미래값을 예측하는 작업

공부시간에 따른 시험점수 예측 (점수)
공부시간에 따른 시험합격여부 예측(합격/불합격)
카드사용패턴

