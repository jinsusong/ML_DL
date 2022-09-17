# ML_DL 용어 및 이론 공부
## 기초 수학 
1. 미분 : 상수는 0으로 무시
2. 편미분 : 미분하는 대상을 제외한 나머지는 무시
3. 합성함수의 미분 : 미분 후 치환한 함수의 미분값을 곱해줌


## 딥러닝 용어

1. 활성화 함수 : 신경망의 뉴런들을 선형 결합한 하면, 선형 모형이 된다. 이를 비선형 모형으로 결합하기 위해서는 활성화 함수가 필요

2. 옵티마이저 : 딥러닝은 뉴런에 적용되는 최적의 가중치 값을 찾기 위해 사용, 최적의 가중치 값은 손실함수(loss function)를 최소화하는 값

3. 손실함수 : 손실함수는 보통 에측값과 실제값의 차이로 정의, 손실함수의 값을 최소화하는 방향으로, 딥러닝의 가중치를 학습시킴,

4. 배치크기 : 배치크기는 딥러닝에 학습할 때, 입력하는 데이터의 수

5. 에포크 : 에포크는 학습 횟수이다. 에포크가 1이면 전체 데이터를 한 번 학습한다

6. 학습률 : 학습률은 기울기의 반대방향으로 이동할 때, 그 학습비율을 말함

## ML 종류 

1. 지도학습
2. 비지도학습
3. 강화학습

## 이진분류 성능 평가 

1. Accuracy ( 정확도 ) : Accuracy는 실제 데이터에서 예측 데이터가 얼마나 같은지를 판단하는 단순한 지표

- 한계 : 이진 분류의 경우, 데이터의 구성에 따라 모델의 성능을 왜곡할 수 있기 때문에 정확도 수치 하나만 가지고 성능을 평가하지 않는다.
정확도는 불균형한 레이블 값 분포에서 분류 모델의 성능을 판단할 경우, 적합한 평가 지표가 아니다.
Confusion Matrix ( 오차 행렬 ) : 이진 분류에서 예측 오류가 얼마인지와 더불어 어떠한 유형의 예측 오류가 발생하고 있는지를 함께 나타내는 지표

-  True/False: 실제와 예측이 일치하는가?
-  Positive/Negative: 뭘로 예측했는가?

-  TN(True Negative, Negative Negative): 실제는 Negative인데, Negative로 예측함.
-  FP(False Positive, Negative Positive): 실제는 Negative인데, Positive로 예측함.
-  FN(False Negative, Positive Negative): 실제는 Positive인데, Negative로 예측함.
-  TP(True Positive, Positive Positive): 실제는 Positive인데, Positive로 예측함.
-  불균형한 레이블 클래스를 가지는 데이터에서는

-  많은 데이터 중 중점적으로 찾아야 하는 매우 적은 수의 레이블에 1,  그렇지 않은 경우에 0을 부여하는 경우가 많다.

2. Precision ( 정밀도 ) , Recall ( 재현율 )

-  Precision : FP(실제는 0인데 예측은 1)을 낮추는 데에 초점
-  Recall : FN(실제는 1인데 예측 0)을 낮추는 데에 초점

-  Task에 따른 Precision, Recall의 상대적 중요도 : 보통은 Recall이 Positive보다 상대적으로 중요한 업무가 많지만, Precision이 더 중요한 지표인 경우도 있다.

-  Recall이 중요한 케이스 : 암 검출, 금융사기 검출 같은 Task에서는 실제로 Positive인 얘들을 Negative로 예측하면 큰일난다.
-  Precision이 중요한 케이스 : 스팸 검출 같은 Task에서는 실제로 Negative인 얘들을 Positive로 예측하면 큰일난다.
-  Precision/Recall Trade-off : recision과 Recall은 상호 보완적인 평가 지표이기 때문에 어느 한 쪽을 강제로 높이면 다른 하나의 수치는 떨어지기 쉽다. 이를 Precision/Recall Trade-off라고 부른다.

3. F1 score : F1 Score는 Precision과 Recall을 결합한 지표, Precision과 Recall이 어느 한 쪽으로 치우치지 않을 때 상대적으로 높은 값을 가진다.

4. ROC Curve, AUC Score : ROC Curve와 이에 기반한 AUC Score는 이진 분류의 예측 성능 측정에서 중요하게 사용되는 지표

  - ROC Curve : ROC Curve가 가운데 직선에 가까울수록 성능이 떨어지는 것이며, 멀어질수록 성능이 뛰어난 것

  - FPR(False Positive Rate)이 변할 때 TPR(True Positive Rate)이 어떻게 변하는지를 나타내는 곡선
  - FPR을 X축으로, TPR을 Y축으로 잡은 그래프
  - TPR(민감도) : 실제 값 Positive가 정확히 예측되어야 하는 수준 , Recall과 정의가 같
  - FPR : 1-TNR (특이성) : 실제 값 Negative가 정확히 예측되어야 하는 수준
  - ROC-AUC Score : 결국 분류의 성능 지표로 사용되는 것은 ROC 곡선 면적에 기반한 AUC(Area Under Curve) 값

  - AUC(Area Under Curve) 값은 ROC 곡선 밑의 면적을 구한 것으로, 1에 가까울수록 좋은 수치
  - AUC 값이 커지려면, FPR이 작은 상태에서 알마나 큰 TPR을 얻을 수 있느냐가 관건
