# 회고

학습 그래프 추이 | 생성 이미지 변화 추이
:--:|:--:
![img1](https://github.com/ethan-yoo/2022_AIFFEL/blob/main/Exploration/E14/gifs/dcgan_history.gif) | ![img2](https://github.com/ethan-yoo/2022_AIFFEL/blob/main/Exploration/E14/gifs/fashion_mnist_dcgan.gif)
![img3](https://github.com/ethan-yoo/2022_AIFFEL/blob/main/Exploration/E14/gifs/re_history.gif) | ![img4](https://github.com/ethan-yoo/2022_AIFFEL/blob/main/Exploration/E14/gifs/re_gan.gif)

위쪽 그래프는 epoch 300, batch_size 256일 때이고 아래 그래프는 epoch 500, batch_size 128일 때 입니다.

아래쪽 그래프를 보면 iteration이 반복됨에 따라서 real accuracy가 향상되는 걸 볼 수 있습니다. 또한 fake accuracy가 조금씩 낮아지긴 하지만 real보다 높은 걸로 봐서는 판별자가 fake에 예민해서 여차하면 바로 fake image로 분류하는 경향이 있는 것 같습니다.

이를 개선하기 위해서는 판별자가 total_loss를 산출할 때 fake_loss 값을 덜 보게 가중치를 주어서 덜 예민하게 만들어주면 될 것 같습니다.
