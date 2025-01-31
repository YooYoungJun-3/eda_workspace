EDA 보고서

주제: 운동 빈도와 운동 유형이 체지방 비율에 미치는 영향

1. 헬스장 회원 데이터의 소개 및 분석 방향

	1.	데이터 출처: Kaggle
(https://www.kaggle.com/datasets/valakhorasani/gym-members-exercise-dataset)
	•	해당 데이터셋은 헬스장 회원의 운동 루틴, 신체적 특징, 피트니스 지표에 대한 정보를 포함하고 있습니다.
	•	심박수, 소모 칼로리, 운동 시간과 같은 성과 지표 외에도 인구 통계 정보 및 운동 경험 수준을 포함하여 다양한 분석이 가능함.
	2.	탐색 목적: 운동 빈도와 운동 유형이 체지방 비율에 미치는 영향을 파악하고, 이를 선형 회귀 모델을 통해 분석합니다.

2. 데이터 소개

	•	주요 컬럼은 다음과 같습니다:
	•	Workout_Frequency (days/week): 주간 운동 빈도
	•	Workout_Type: 운동 종류 (Cardio, Strength, HIIT, Yoga)
	•	Fat_Percentage: 체지방 비율

3. 주제별 자료분석 및 해석

1. 기초 통계 및 데이터 구조 확인

	•	데이터 샘플 (head): 데이터의 상단부를 출력하여 데이터를 확인하였습니다.
	•	info(): 데이터 타입과 기초 정보를 파악하였으며, 결측치는 없는 것으로 확인되었습니다.
	•	describe(): 각 변수의 주요 통계를 확인하여 운동 빈도와 체지방 비율의 평균, 표준 편차, 최댓값과 최솟값 등을 확인하였습니다.
	•	운동 유형 확인: Workout_Type은 Cardio, Strength, HIIT, Yoga의 4가지 유형으로 구성됨을 확인했습니다.

2. 변수 간 관계 시각화

(1) 운동 빈도와 체지방 비율의 관계

	•	산점도 분석: 주간 운동 빈도(Workout_Frequency)와 체지방 비율(Fat_Percentage)의 관계를 산점도로 시각화하여, 두 변수 간의 상관 관계를 확인하였습니다.
	•	결과 해석: 운동 빈도가 높아질수록 체지방 비율이 낮아지는 경향이 보였으나, 모든 데이터에서 뚜렷한 선형 관계를 보이지는 않았습니다.

(2) 운동 유형과 체지방 비율의 관계

	•	박스플롯 분석: 운동 유형별로 체지방 비율 분포를 비교하기 위해 박스플롯을 사용했습니다.
	•	결과 해석: HIIT와 Strength 운동을 하는 그룹이 상대적으로 체지방 비율이 낮은 경향을 보였으며, 요가와 유산소 운동(Cardio)을 하는 그룹은 체지방 비율이 약간 높은 편임을 확인했습니다.

3. 선형 회귀 모델 적용 및 결과 해석

	•	모델 적용: Workout_Frequency, Workout_Type을 독립 변수로, Fat_Percentage를 종속 변수로 하여 Lasso 회귀 모델을 적용했습니다.
	•	평가 지표: 모델의 성능을 평가하기 위해 MSE(Mean Squared Error)를 사용했으며, MSE 값은 약 28.27로 나타났습니다.
	•	회귀 모델 해석:
	•	Workout_Frequency는 체지방 비율을 줄이는 데 긍정적인 영향을 미치는 것으로 나타났습니다. 즉, 운동 빈도가 높아질수록 체지방 비율이 낮아지는 경향이 확인되었습니다.
	•	Workout_Type 변수 중 HIIT와 Strength가 체지방 비율에 더 큰 영향을 미치는 것으로 나타났으며, 요가나 유산소 운동은 상대적으로 영향이 적었습니다.

4. 결론

	1.	운동 빈도의 영향: 주간 운동 빈도가 높아질수록 체지방 비율이 낮아지는 경향이 확인되었으나, 모든 경우에 해당되는 것은 아님을 주의해야 합니다.
	2.	운동 유형의 영향: HIIT와 Strength와 같은 강도 높은 운동이 체지방 비율을 낮추는 데 더 효과적이라는 결과가 나타났습니다.
	3.	모델 성능: Lasso 회귀 모델의 MSE 값은 28.27로, 비교적 정확한 예측을 제공하지만 더 낮은 오차를 위한 모델 개선 여지가 남아 있습니다.

5. 향후 분석 방향

	•	더 많은 변수 추가: 칼로리 소모량, 운동 시간 등의 변수들을 추가하여 체지방 비율에 영향을 미치는 더 복합적인 요인을 분석할 수 있습니다.
	•	비선형 모델 사용: 랜덤 포레스트와 같은 비선형 모델을 사용하여 체지방 비율과 운동 습관 간의 비선형 관계를 분석할 수 있습니다.
	•	개별 특성에 따른 모델 최적화: 성별, 연령대별로 모델을 구분하여 맞춤형 분석을 통해 더 정교한 결과를 도출할 수 있습니다.