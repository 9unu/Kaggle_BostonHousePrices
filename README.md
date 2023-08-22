# Kaggle "House Prices - Advanced Regression Techniques"

## 파일 구조

### 1. 최종 모델 파일 (`modeling.ipynb`)
이 파일에는 최종 모델이 저장되어 있습니다.

### 2. EDA 폴더
#### `order_data.ipynb`
- 카테고리형 및 숫자형 특성 중 순서형 성질을 가진 특성을 구별하여 pickle 파일에 저장
- 저장된 결과: `category_order`, `numeric_order`, `numeric_con`, `total_encode`

#### `target_dist.ipynb`
- 'SalePrice' 예측값의 분포 확인
- 로그 변환을 통해 right skew 보정

#### `missing_value.ipynb`
- 각 특성의 결측치 처리 방법 결정
- 최빈값, 평균값, SQL을 이용한 조건부 중앙값, 비율에 기반한 결측값 처리

#### `skew_feature.ipynb`
- 왜도가 심한 숫자형 특성 확인
- 로그 정규화를 통한 보정

### 3. `function_file.ipynb`
이 파일에는 편의를 위해 작성한 함수들이 모아져 있습니다. 모델링 파일에서 import하여 사용 가능한 함수들이 포함되어 있습니다.

#### `top_n_feature(original_list, top_n)`
주어진 리스트에서 상위 N개의 특성을 선택하는 함수

#### `model_val(model, X_train, y_train)`
모델의 성능을 검증하는 함수로, 학습 데이터에 대한 교차 검증 결과 반환 (RMSE 평균, RMSE 표준편차)

#### `feature_importance(model, X_train, top_n=30)`
모델의 특성 중요도를 계산하고 상위 N개 특성을 반환하는 함수

#### `visualize_model_predictions(model, X_test, y_test)`
모델의 예측 결과를 시각화하여 실제값과 비교하는 함수

#### `Regression_coef(model, X_train, top_n=30)`
회귀 모델의 계수 값을 계산하고 상위 N개를 반환하는 함수
