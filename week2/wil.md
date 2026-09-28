# Weekly I Learned

### 강의 내용
학습이란 cost function이 더 낮아지도록 조정하는 일
Gradient Descent, Back Propagation
Gradient를 구해서 가중치를 조금씩 움직임. Back Propagation을 통해 빠르게 Gradient 계산
parameter, hyper parameter
학습을 통해 바뀌어가는 것 : 파라미터
학습 전 정하는 것 : hyper 파라미터
옵티마이저의 선택도 하이퍼 파라미터이다.

### 실제로 Gradient를 구하는 과정, Back Propagation
a, b의 변화에 따른 L의 변화율을 구하기 위해 편미분값을 곱함 (체인룰)
심화실습에서는 dL/dy를 구한 후 dy/da, dy/db를 곱하고 데이터별 결과를 합해 그래디언트를 구하는 함수를 구현해보았다.

### Optimizer로 업데이트
구한 그래디언트를 이용하여 current_params - learning_rate * gradient를 반환하는 update 함수를 구현해보았다.

### batch의 개념
전체 학습 데이터를 batch 단위로 나눠서 구간별로 학습시키는데 그 이유는 계산 효율 + 학습 특성 때문이다
batch의 크기가 크면 안정적이지만 업데이트 횟수가 작고, 메모리 문제도 있을 수 있다.
batch의 크기가 작으면 자주 업데이트하는대신 gradient가 많이 흔들린다.

### learning_rate
learning_rate가 너무 작을 경우에는 학습 효과가 미미하고, 너무 큰 경우에는 최적점을 지나칠 수 있다.

### Optimizer 종류별 비교
SGD : 현재 gradient만 본다
SGD + Momentum : 과거 방향을 기억 -> 진동을 감소하고 진행방향으로는 가속한다
RMSprop : gradient의 방향을 누적하는 게 아닌 제곱을 누적한다 -> 계산식에 따라 gradient가 계속 큰 파라미터는 조심스러워지고, 작은 파라미터는 상대적으로 더 크게 움직인다
Adam : Momentum + RMSprop -> 방향과 크기 둘의 누적 정보를 모두 사용, 둘의 장점을 합함

자주 비교되는 핵심 조합은 SGD + Momentum vs Adam이라고 한다.
초반 학습은 Adam이 빠른 경우가 많고, 최종 성능은 hyper parameter가 잘 튜닝된 SGD + Momentum이 Adam보다 더 좋은 일반화를 내는 경우도 있다고 한다.

### 마무리
Back Propagation을 처음 배울 때는 역전파라는 말이 추상적으로 느껴졌는데, 각 파라미터에 대한 로스의 변화율(gradient)을 체인룰을 통해 계산하는 과정이라는 것이 심화 과정을 진행하며 잡혔다.