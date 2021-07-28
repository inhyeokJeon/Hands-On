1. 백만 개의 샘플을 가진 훈련 세트에서 (규제 없이) 훈려니킨 결정 트리의 깊이는 대략 얼마일까요 ?
> log2(m)
2. 한 노드의 지니 불순도가 보통 그 부모보다 작을까요, 아니면 클까요? 일반적으로 작거나 클까요, 아니면 항상 작거나 클까요?
> 일반적으로 부모노드의 지니 불순도 보다 작다.
3. 결정 트리가 훈련 세트에 과대적합되었다면 max_depth를 줄이는 것이 좋을까요?
> max_dapth 를 줄여 규제를 늘이는 것이 좋다.
4. 결정 트리가 훈련 세트에 과소적합되었다면 입력 특성의 스케일을 조정하는 것이 좋을까요?
> 결정 트리는 훈련 데이터의 스케일이나 원점에 맞추어져 있는지 상관하지 않는다. 이것이 결정트리의 장점중 하나이다.
> 그러므로 결정 트리가 훈련 세트에 과소적합 되었다고 해서 입력 특성의 스케일을 조정하는것은 시간낭비이다.
5. 백만 개의 샘플을 가진 훈련 세트에 결정 트리를 훈련시키는데 한 시간이 걸렸다면, 천만개의 샘플을 가진 훈련 세트에 결정 트리를 훈련시키는 데는 대략 얼마나 걸릴까요?
> 11.7시간
6. 십만 개의 샘플을 가진 훈련 세트가 있다면 presort=True로 지정하는 것이 훈련 속도를 높힐까요?
> 아니요 훈련 세트가 클 경우 정렬 시키는데 시간이 많이 걸리기 때문에 훈련 속도가 떨어질 것이다.
Try