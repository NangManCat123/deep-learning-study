# Weekly I Learned

## CNN과 Dense Layer의 차이
- Dense Layer는 Flatten을 통해 이미지를 1차원으로 펼쳐서 사용하기 때문에 픽셀 간의 공간적 관계를 직접적으로 활용하지 못한다.
- CNN은 작은 kernel을 이미지 전체에 이동시키면서 주변 픽셀들의 관계를 학습한다. 같은 kernel을 여러 위치에서 사용하므로 파라미터 수도 효율적으로 관리할 수 있다.

## Convolution, Padding, Pooling
- Convolution : 이미지의 일부분과 kernel을 원소별로 곱한 후 합산하여 feature map을 생성한다.
- Padding : 이미지 테두리에 0을 추가해 출력 크기를 조절하고 가장자리 정보도 활용할 수 있게 한다.
- Stride : kernel이 한 번에 이동하는 칸 수
- Max Pooling : 일정 영역에서 최댓값만 남겨 feature map의 크기를 줄인다.

## NumPy로 직접 구현
이번에는 zero padding, convolution, max pooling을 직접 구현해보았다. 배열 슬라이싱으로 이미지의 특정 영역을 가져와 kernel과 곱하고 합산하는 과정을 구현하면서 CNN이 실제로 어떻게 이미지를 처리하는지 이해할 수 있었다.

## LeNet과 AlexNet
LeNet-like와 AlexNet-like를 직접 구성하고 Fashion-MNIST로 학습시켜보았다. 처음에는 LeNet-like의 정확도가 가장 높을 것으로 예상했지만, 실제로는 AlexNet-like가  가장 높았고 단순 CNN도 LeNet-like보다 좋은 결과를 보였다.

## 마무리
모델이 복잡하다고 반드시 정확도가 높은 것은 아니지만, 이번 실습에서는 가장 많은 파라미터를 가진 AlexNet-like가 가장 좋은 성능을 보였다. 모델을 선택할 때는 정확도뿐 아니라 데이터의 특성과 파라미터 수, 과적합 가능성도 함께 고려해야 한다.