과적합(overfitting)은 머신러닝 모델이 학습 데이터에 지나치게 적합해져서, 새로운 데이터(테스트 데이터나 실제 환경 데이터)에 대해 일반화(generalization) 능력이 떨어지는 현상을 말함. 즉, 모델이 학습 데이터의 세부적인 패턴이나 노이즈까지 과도하게 학습해버려, 보지 못한 데이터에 대해서는 성능이 저하되는 경우임.

---

### 과적합의 특징
1. **학습 데이터에 대한 높은 성능**  
   - 훈련 데이터(train set)에서는 정확도나 손실 함수 값이 매우 우수.
1. **테스트 데이터에 대한 낮은 성능**  
   - 검증 데이터(validation set)나 테스트 데이터(test set)에서는 성능이 떨어짐.
3. **복잡한 모델에서 자주 발생**  
   - 모델이 너무 많은 파라미터를 가지거나, 층이 지나치게 깊을 때 발생하기 쉬움.

---

### 과적합이 발생하는 원인
1. **데이터 부족**  
   - 학습 데이터가 너무 적거나 다양성이 부족하면, 모델이 그 데이터에만 특화되기 쉬움
1. **모델 복잡도 과다**  
   - 뉴런 수가 많거나 층이 깊은 신경망, 또는 과도한 특징(feature)을 사용할 때 발생할 수 있음
1. **노이즈 학습**  
   - 데이터에 포함된 무작위 노이즈나 이상치(outlier)를 모델이 패턴으로 잘못 인식함
1. **충분한 정규화 부족**  
   - 정규화(regularization) 기법이나 드롭아웃 같은 방법이 적용되지 않으면 과적합 위험이 높아짐
1. **과도한 학습 반복(epoch)**  
   - 너무 많은 학습 반복은 모델이 학습 데이터를 "외우는" 결과를 초래할 수 있음
---

### 과적합의 예시
예를 들어, 학생이 시험 대비 공부를 한다고 가정:
- **정상 학습**: 시험에 나올 법한 주요 개념을 골고루 학습해서 다양한 문제를 풀 수 있음.
- **과적합**: 연습 문제 몇 개만 반복해서 외워버려서, 그 문제는 잘 풀지만 새로운 문제는 풀지 못함.

모델이 훈련 데이터만 잘 맞추고, 새로운 데이터에 대해서는 예측을 실패함

---

### 과적합 확인 방법
1. **훈련 vs 검증 손실 비교**  
   - 훈련 손실(train loss)은 계속 감소하지만, 검증 손실(validation loss)이 증가하기 시작하면 과적합의 신호
1. **학습 곡선(Learning Curve)**  
   - 훈련 데이터와 검증 데이터의 성능 차이가 점점 벌어지는지 확인
1. **테스트 성능 저하**  
   - 테스트 데이터에서 예측 정확도가 낮아지는 경우

---

### 과적합 방지 방법
1. **더 많은 데이터 수집**  
   - 데이터 양과 다양성을 늘리면 모델이 일반화된 패턴을 학습하기 쉬워짐
1. **데이터 증강(Data Augmentation)**  
   - 이미지 회전, 크기 조정 등으로 데이터를 인위적으로 늘려 다양성을 확보
1. **모델 단순화**  
   - 층 수나 뉴런 수를 줄여 모델의 복잡도를 감소
1. **정규화(Regularization)**  
   - L1, L2 정규화로 가중치 크기를 제한하거나, 손실 함수에 페널티를 추가
1. **드롭아웃(Dropout)**  
   - 학습 중 일부 뉴런을 무작위로 비활성화해 모델의 과도한 의존성을 감소
1. **조기 종료(Early Stopping)**  
   - 검증 손실이 더 이상 개선되지 않을 때 학습을 중지
1. **교차 검증(Cross-Validation)**  
   - 데이터를 여러 폴드로 나눠 모델의 일반화 성능을 평가

---

### 예시 코드 (TensorFlow)
드롭아웃과 조기 종료를 적용한 간단한 예시:
```python
from tensorflow import keras
from tensorflow.keras import layers

model = keras.Sequential([
    layers.Dense(16, activation="relu"),
    layers.Dropout(0.2),  # 20% 뉴런 비활성화
    layers.Dense(16, activation="relu"),
    layers.Dropout(0.2),
    layers.Dense(1, activation="sigmoid")
])

model.compile(optimizer="adam", loss="binary_crossentropy", metrics=["accuracy"])

# 조기 종료 설정
early_stopping = keras.callbacks.EarlyStopping(monitor="val_loss", patience=10)

# 모델 학습
history = model.fit(x_train, y_train, epochs=100, validation_split=0.2, callbacks=[early_stopping])
```

---

### 결론
- 과적합은 모델이 학습 데이터를 "너무 잘" 맞추는 바람에 새로운 데이터에 적응하지 못하는 문제임
- 이를 방지하려면 데이터, 모델 구조, 학습 과정에서 적절한 조정을 해야 함