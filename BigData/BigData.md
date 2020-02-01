# Big Data

## Required Knowledge for Deep Learning

* DB 에서 오차를 ERROR라 표현

1. ### Linear  Classifier

   * 분류를 위한 요소는 Domain  knowledge(전문가 집단을 통해 정함)
   * 전문가의 도움이 없다면 최소한 요소 설정의 합리적 근거 필요
   * 정한 두 개의 요소 A, B를 이용해  Y = A * X + B의 연산식을 정함
   * 여러 개의 실제 데이터 X, Y 값을 대입해 적당한 A, B값 산출
   * ERROR : 연산식을 통한 Y값 - 실제 Y값
   * η : Learning Rate
   * T : 분류선
   * T = (A + ERROR/X) * X + B
   * XOR 연산과 같은 경우는 하나의 선으로 분류가 불가능한 단점

2. ### Perceptron

   * Step function(threshold)

3. ### Artificial Neural Network

   * Sigmoid function
   * 미분/편미분 개념 이해 필요

4. ### Deep Learning

   * ReLu function 