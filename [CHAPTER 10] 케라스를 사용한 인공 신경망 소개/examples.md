# 연습문제 !! 드가자

> 2. (그림[10-3]에 있는 것과 같은) 초창기 인공 뉴런을 사용해 식을 완성하세요 p408 check it
> > [ 이미지 참고. 355p]
> 3. 고전적인 퍼셉트론 (즉, 퍼셉트론 훈련 알고리즘으로 훈련된 단일 TLU)보다 로지스틱 회귀 부류기를 일반적으로 선호하는 이뉴는 무엇인가요?
> 퍼셉트론을 어떻게 수정하면 로지스틱 회귀 분류기와 동등하게 만들 수 있나요?
> > * 퍼셉트론은 클래스 확률을 제공하지 않으며 고정된 임계값을 기준으로 예측을 만든다. 데이터 셋이 선형으로 구분될 때만 수렴한다. 이런 이유로 로지스틱 회귀를 선호함.
> > * 활성화 함수로 로지스틱 활성화 함수로 사용하고, 경사 하강법을 사용하여 훈련시키면 로지스틱 회귀 분류기와 동일하게 된다. 
> 4. 왜 초창기의 다층 퍼셉트론을 훈련할 때 로지스틱 활성화 함수가 핵심 요소였나요?
> > 로지스틱 활성화 함수의 도함수는 어디에서나 0이 아니어서 경하하강법이 항상 경사를 따라 이동할수 있으므로 초창기 MLP의 핵심 요소였다.
> > 활성화 함수가 계단 함수일 때는 경사가 없기 때문에 경사 하강법이 이동할 수 없기때문.
> 5. 인기 많은 활성화 함수 세 가지는 무엇인가요? 이를 그려볼 수 있나요?
> > [그림 10-8 참조] 
> 6. 통과 뉴런 10개로 구성된 입력층, 뉴런 50개로 구성된 은닉층, 뉴런 3개로 구성된 출력층으로 이루어진 다층 퍼셉트론이 있다고 가정합시다.
> 모든 뉴런은 ReLU 활성화 함수를 사용합니다.
> -> m 은 훈련 배치 크기를 나타낸다.
> * 입력 행렬 X의 크기는 얼마인가요? m x 10
> * 은닉층의 가중치 벡터 Wh와 편향 벡터 bh의 크기는 얼마인가요? 10 x 50, 편향벡터 = 50
> * 출력층의 가중치 벡터 Wo와 편향 벡터 bo의 크기는 얼마인가요? 50 x 3, 편향벡터 = 3
> * 네트워크의 출력 행렬 의 크기는 얾마인가요? m x 3
> * X, Wh, bk, Wo, bo의 함수를 네트워크의 출력 행렬 Y를 계산하는 식을 써보세요. 
> > Y = ReLu(ReLu(XWh+bh)Wo+bo) -> ReLU 함수는 행렬에 있는 음수를 무조건 0으로 만듬. 
> 편향 벡터를 행렬에 더하면 행렬의 모든 행에 덧셈이 각기 적용되는 브로드캐스팅이 일어납니다.
> 7. 스팸 메일을 분류하기 위해서는 출력층에 몇 개의 뉴런이 필요할까요? 출력층에 어떤 활성화 함수를 사용해야 할까요?
>  MNIST 문제라면 출력층을 어떤 활성하 함수를 사용하고 뉴런을 몇 개가 필요할까요? 
>  2장에서 본 주택 가격 예측용 네트워크에 대해 같은 질문의 답을 찾아보세요.
> > 1개의 뉴런이 필요하다 스팸인지 아닌지만 구별하면 되기 때문. 확률을 추청 할 때 일반적을 로지스틱 활성화 함수를 사용.
> > 10개의 뉴런이 필요하다, 다중 클래스환경에서 클래스마다 하나의 확률을 출력하기 위해 로지스틱 함수를 소프트맥스 활성화 함수로 바꾸어야 한다.
> > 출력층에 활성화 함수가 없는 출력 뉴런 하나가 필요하다.
> 8. 역전파란 무엇이고 어떻게 작동하나요? 역전파와 후진 모드 자동 미분의 차이점은 무엇인가요?
> > * 역전파는 인공신경망을 훈련시키는 하나의 기법. 먼저 모델의 모든 파라미터에 대한 비용 함수의 그레디언트를 계산하고,
> 이 그레디언트를 사용해 경사 하강법 스텝을 수행.
> > * 역전파 단계는 모델 파라미터가 비용 함수를 최소화하는 값으로 수렴할 때까지 훈련 배치에서 일반적으로 수천, 수백만 번 수행된다.
> 그레디언트를 계산하기위해서는 후진 모드 자동 미분을 사용.
> > * 후진 모드 자동 미분은 계산 그래프의 정방향 계산에서 현재 훈련 배치에 대한 모든 노드의 값을 구한다.
> 그 다음에 역방향 계산에서 한번에 모든 그래디언트를 구한다. 
> > * 역전파는 그래디언트 계산과 경사 하강법 스텝을 여러번 수행하여 인공 신경망을 훈련시키는 전체 프로세스를 의미.
> > * 반면 후진 모드 자동 미분은 그래디언트를 효과적으로 계산하는 하나의 기법으로 역전파에서 사용됨.
> 9. 다층 퍼셉트론에서 조정할 수 있는 하이퍼파라미터를 모두 나열해보세요. 훈련 데이터에 다층 퍼셉트론이 과대적합되었다면 이를 해결하기 위해 
> 하이퍼 파라미터를 어떻게 조정해야 할까요?
> > * 은닉층 수, 각 은닉층의 뉴런 수, 각 은니층과 출력층에서 사용하는 활성화 함수. 일반적으로 ReLU가 좋음. 
> > * 이진 분류에선는 로지스틱 활성화 함수, 다중 분류에서는 소프트맥스 활성화 함수를 사용하고 회귀에서는 활성화 함수를 사용하지 않음.
> > * MLP가 과대적합되었으면 은닉층 수와 각 은닉층에 있는 뉴런 수를 줄여야한다.