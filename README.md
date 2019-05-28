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

#### 1. 튜닝 값 : Ensemble을 구성하는 모든 모델의 n_estimators, lr, max_samples, max_depth, max_iter_predict, alpha, gamma
  - n_estimators : Random Forest의 트리 수
  - lr : 학습률
  - max_samples : 트리를 구성할 때 각기 다른 트리로 구성해야 하므로 무작위로 데이터의 샘플을 반복 추출한다.
  - max_depth : 트리의 최대 depth
  - gamma : 감마 파라미터는 훈련 샘플이 결정 경계에 미치는 영향을 조절한다.
 
#### 2. 참고
  - https://tensorflow.blog/%ED%95%B8%EC%A6%88%EC%98%A8-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-1%EC%9E%A5-2%EC%9E%A5/2-7-%EB%AA%A8%EB%8D%B8-%EC%84%B8%EB%B6%80-%ED%8A%9C%EB%8B%9D/
  - 사이킷런의 GridSearchCV를 사용하면 탐색하고자 하는 하이퍼파라미터와 시도해볼 값을 지정하여 다양한 튜닝을 자동으로 시도해볼 수 있다.
  - 어떤 하이퍼파라미터 값을 지정해야 할지 모를 때는 연속된 10의 거듭제곱 수로 시도해보는 것도 좋다.
  
#### 3. 분석
  - 튜닝을 할 수록 성능이 좋아졌지만, 1000 times 이후부터 overfit이 일어났다.
 
### (2) 나영채
| Experiment | Score | Date |
|---|:---:|---:|
| Original Kernel : 😁 Simplest Top 10% Titanic [0.80861] | 0.80861 / 0.77990 / 0.78947 / 0.80861 | 2019.05.25 |

#### 1. 튜닝값 : 소폭 튜닝 할게 별로 없음..
위 커널에서 사용하는 데이터 분석에서 임의로 설정한 파라미터에서는 바꿀만한것이 iterations 정도 밖에 없다. 하지만 CV 그래프에서 100이상의 iteration을 할 필요가 없음을 알 수 있기에 튜닝하지않았다.
learning rate는 해볼법 하지만 ...

### (3) 이장후
| Experiment | Score | Date |
|---|:---:|---:|
| Original Kernel : simple titanic kernel for beginner like me | 0.76xxx | 2019.05.16 |
| bootstrap setting - only set bootstrap from False to True | 0.79425 | 2019.05.20 |
| n_estimators setting - bootstrap setting True & set n_estimators single value | 0.79904 | 2019.05.20 |
| n_estimators setting(2) - bootstrap setting True & set n_estimators [20 , 30, 50] | 0.78947 | 2019.05.20 |
| n_estimators setting(3) - bootstrap setting True & set n_estimators [100, 110, 120] | 0.77511 | 2019.05.20 |


#### 1. 튜닝 값 : RandomForest 의 bootstrap, n_estimators. 나머지 파라미터는 의미가 잘 와닿지 않아서 생략하였다.
  - 모델을 제작한 사람은, 여러 가지의 모델로부터 투표를 해서 결정을 해내는 방법을 채택했다.
  - 다양한 모델을 모르기 때문에 하나에만 집중해보기로 했다. 따라서 Random Forest 만 이용해보기로 하였다.
  - bootstrap : bootstrap 추출 여부
  - n_estimators : Random Forest의 트리 수
 
#### 2. 참고
  - 송재욱 pf Question . Bootstrap 에 대한 간단한 조언 - 'Bootstrap 은 강제로 모집단의 크기를 늘리고 싶을 때 사용한다.'
  - Titanic 문제에서는 표본의 크기가 상당히 작은 편이기 때문에 Bootstrap 은 좋은 시도가 될수있을 것 같다고 생각하였다.
  - Youtube StatQuest with Josh Starmer - Random Forest (1), (2)
  - 사이킷런의 GridSearchCV를 사용하면 탐색하고자 하는 하이퍼파라미터와 시도해볼 값을 지정하여 다양한 튜닝을 자동으로 시도해볼 수 있다.
  - 어떤 하이퍼파라미터 값을 지정해야 할지 모를 때는 연속된 10의 거듭제곱 수로 시도해보는 것도 좋다.
  
  - 파라미터 참고
  - min_samples_leaf : "leaf node" 에 요구되는 최소 데이터셋(sample) 갯수입니다. 즉, 이 숫자보다 개수가 높으면 나눈다는 것. 좌우 가지에(이진트리의 경우) 최소 개수를 남기는지 안 남기는지. 어느 깊이에서나 나누어지는 포인트는 오직 저 기준으로 고려됩니다. 회귀분석의 경우, 이것은 모델을 상당히 유하게 만들어 줍니다.
 - min_samples_split : internal node 를 나눌 것으로 요구되는 최소 데이터셋(samples)의 숫자입니다. 즉, 이 숫자보다 개수가 높으면 나눈다는 것.
 - max_depth : 나무의 깊이를 설정합니다. 만약 None 값으로 놓으면, 노드는 언제까지 확장되냐면 1. 모든 "leaf node"들이 "pure"할때 (즉, leaf node 는 무조건 Survived 또는 Not-Survived 둘 중 하나의 값이 들어갈 때까지 확장) 또는 2. 모든 "leaf node"들이 "min_samples_split" 보다 적은 값을 가지게 될 때까지 확장된답니다!
  
#### 3. 분석
  - Feature 의 개수가 10개가량밖에 안 되는데, n_estimators 를 900까지 높일 필요가 있었는가 싶다. 그냥 직관에 의한 튜닝이었다.
  - bootstrap 도 하는 것이 적절하지 않을까? 하는 마음에 수행하게 되었다. 이 또한 직관에 의한 튜닝이었다.
  - 다양한 estimator 을 loop 를 통해 시도해 보았어야 하지만 그러지 못했다.
  - 별도의 test set이 없었기 때문에 스스로 다양한 것들을 시도해보지 못했다. K-fold 를 이용하여 validation set 만 이용할 수 있었다.
  
### (4)

<br>

## 4. Team Score

| Rank/Total | Team | Date |
|---|:---:|---:|
| 140/11434 | SJU-SAI | 2019.05.15 |
