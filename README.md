# SAI-1st_Competition

<br>
<hr>

## 1. Competition
 - Titanic: Machine Learning from Disaster
 - https://www.kaggle.com/c/titanic

<br>

## 2. Team Briefing
 - A Data Science Framework To Achieve 99% Accuracy
 - Simple titanic kernel(82%) for beginner like me 
 - A Comprehensive ML Workflow with Python Titanic: Machine Learning from Disaster
 - Simplest Top 10% Titanic [0.80861]

<br>


## 3. Experiment Result
### (1) 서기원

| Experiment | Score | Date |
|---|:---:|---:|
| Original Kernel : A Data Science Framework To Achieve 99% Accuracy | 0.77990 | 2019.05.16 |
| 0.1 times down grade than the original kernel | 0.77033 | 2019.05.16 |
| 10 times upgrade than the original kernel | 0.77990 | 2019.05.16 |
| 100 times upgrade than the original kernel | 0.78468 | 2019.05.16 |
| 1000 times upgrade than the original kernel | 0.75119 | 2019.05.16 |

 1) 튜닝 값 : Ensemble을 구성하는 모든 모델의 n_estimators, lr, max_samples, max_depth, max_iter_predict, alpha, gamma
  - n_estimators : Random Forest의 트리 수
  - lr : 학습률
  - max_samples : 트리를 구성할 때 각기 다른 트리로 구성해야 하므로 무작위로 데이터의 샘플을 반복 추출한다.
  - max_depth : 트리의 최대 depth
  - gamma : 감마 파라미터는 훈련 샘플이 결정 경계에 미치는 영향을 조절한다.
 
 2) 참고 : https://tensorflow.blog/%ED%95%B8%EC%A6%88%EC%98%A8-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-1%EC%9E%A5-2%EC%9E%A5/2-7-%EB%AA%A8%EB%8D%B8-%EC%84%B8%EB%B6%80-%ED%8A%9C%EB%8B%9D/
  - 사이킷런의 GridSearchCV를 사용하면 탐색하고자 하는 하이퍼파라미터와 시도해볼 값을 지정하여 다양한 튜닝을 자동으로 시도해볼 수 있다.
  - 어떤 하이퍼파라미터 값을 지정해야 할지 모를 때는 연속된 10의 거듭제곱 수로 시도해보는 것도 좋다.
  
 3) 분석
  - 튜닝을 할 수록 성능이 좋아졌지만, 1000 times 이후부터 overfit이 일어났다.
 
### (2)
| Experiment | Score | Date |
|---|:---:|---:|

 - 튜닝 값 : 

### (3)
### (4)

<br>

## 4. Team Score

| Rank/Total | Team | Date |
|---|:---:|---:|
| 140/11434 | SJU-SAI | 2019.05.15 |
