> 1. 군집을 어떻게 정의할 수 있나요? 몇 개의 군집 알고리즘을 말해보세요.
> * 비슷한 샘플을 구별해 하나의 클러스터 또는 비슷한 샘플의 그룹으로 할당하는 작업입니다.
> * k-평균과, DBSCAN, 병합군집, BIRCH, 평균-이동, 유사도 전파, 스펙트럼 군집이 있습니다.
> * 가우시안 혼합 모델
> 2. 군집 알고리즘의 주요 애플리케이션은 무엇인가요?
> * 데이터 분석, 고객 분류, 추천 시스템, 검색 엔진, 이미지 분할,
> * 비선형 차원 축소, 준지도 학습, 이상치 탐지등. 
> 3. k-평균을 사용할 때 적절한 클러스터 개수를 선택할 수 있는 두 가지 기법을 설명하세요.
> * 엘보규칙 - 클러스터 개수의 함수로 이니셔를 그리고 그래프에서 이니셔가 더는 빠르게 감소하지 않는 지점을 찾는다(꺽이는 부분).
> * 일반적으로 이 지점이 최적의 클러스터 개수에 가깝다.
> * 실루엣 점수로 그래프 적용 p 313
> 4. 레이블 전파는 무엇인가요? 왜 이를 구현해야 하고 어떻게 구현할 수 있나요?
> * 레이블이 있는 샘플을 레이블이 없는 샘플에 복사하는 기법이다. 레이블을 가진 샘플의 수를 증가 시킬 수 있어서 효과적이다. 
> * Ex ) k-평균과 같은 경우 센트로이드와 가장 가까운 샘플 중에 레이블이 없는 것에 레이블을 부여한다.
> 5. 대규모 데이터셋으로 확장할 수 있는 군집 알고리즘 두 개를 말해보세요.
>    밀도가 높은지역을 찾는 군집 알고리즘 두 개는 무엇인가요?
> * K-평균, BIRCH이 대규모 데이터 셋에 이용 가능
> * DBSCAN과 평균-이동이 밀도가 높은 지역을 찾는다.
> 6. 능동 학습이 유용한 경우는 언제인가요? 어떻게 구현할 수 있나요?
> * 레이블이 없는 샘플이많고, 비용이 많이 들 때는 능동학습이 유용하다
> * 전문가가 학습 알고리즘과 상호작용하여 알고리즘이 요청하는 특정 샘플에 레이블을 제공한다.
> 7. 이상치 탐지와 특이치 탐지의 차이는 무엇인가요?
> * 이상치 탐지는 이상치가 포함 될 수 있는 데이터셋에서 알고리즘을 훈련한다. 목표는 이상치와 새로운 샘플 사이에 있는 이상치를 구별해 내는 것이다.
> * 특이치 탐지는 깨끗하다고 가정한 데이터 셋에서 알고리즘을 훈련합니다. 새로운 샘플 사이에서 특이한 것을 탐지하는 것입니다. 
> 8. 가우시안 혼합이 무엇인가요? 어떤 작업에 사용할 수 있나요?
> * 가우시안 혼합 모델은 샘플이 파라미터를 모르는 몇 개의 가우시안 분포에서 생성되었다고 가정하는 확률 모델입니다. 
> * 다른 말로 하면 데이가 유한한 개수의 타원 모양 클러스터로 그룹지어 있다는 가정입니다. 하지만 샘플이 어떤 클러스터에 속해 있는지모른다.
> * 밀집도, 추정,군집, 이상치 탐지에 사용된다.
> 9. 가우시안 혼합 모델을 사용할 때 적절한 클러스터 개수를 찾는 두 가지 기법을 말해보세요.
> * BIC나 AIC 그래프를 그리는 것이다. 그다음 BIC나 AIC를 최소화하는 클러스터 개수를 선택한다.
> * 베이즈 가우시안 혼합 모델을 사용해 클러스터 개수를 자동으로 선택하는 것이다.