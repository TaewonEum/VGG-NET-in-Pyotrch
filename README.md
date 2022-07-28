# VGG-NET


VGG NET 구조

![image](https://user-images.githubusercontent.com/104436260/180681477-2ab676ed-e5bb-41ad-b8a9-35757fdc6f70.png)

VGG16 기준으로 Model 생성


구조(VGG 16)
======

input(224x224x3)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=64)->batch norm->activation function(ReLU)

input(224x224x64)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=64)->batch norm->activation function(ReLU)

Maxpooling(filter size=2x2, stride=2x2)-> data size=112x112x64

input(112x112x64)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=128)->batch norm->activation function(ReLU)

input(112x112x128)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=128)->batch norm->activation function(ReLU)

Maxpooling(filter size=2x2, stride=2x2)-> data size=56x56x128

input(56x56x128)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=256)->batch norm->activation function(ReLU)

input(56x56x256)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=256)->batch norm->activation function(ReLU)

input(56x56x256)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=256)->batch norm->activation function(ReLU)

Maxpooling(filter size=2x2, stride=2x2)-> data size=28x28x256

input(28x28x256)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=512)->batch norm->activation function(ReLU)

input(28x28x512)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=512)->batch norm->activation function(ReLU)

input(28x28x512)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=512)->batch norm->activation function(ReLU)

Maxpooling(filter size=2x2, stride=2x2)-> data size=14x14x512

input(14x14x512)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=512)->batch norm->activation function(ReLU)

input(14x14x512)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=512)->batch norm->activation function(ReLU)

input(14x14x512)->convolution(filter size=3x3, stride=1x1, padding=1x1, out_channles=512)->batch norm->activation function(ReLU)

Maxpooling(filter size=2x2, stride=2x2)-> data size=7x7x512

dense layer -> 7x7x512=25088 길이를 가진 vector로 변환

fully connected layer(input vector->activation funtion->Drop out)-> 25088->2048개 Node로 반환

fully connected layer(input vector->activation function->Drop out)->2048->1024

fully connected(input vector(1024)->number of class)

define VggNet class
====

- import library

![image](https://user-images.githubusercontent.com/104436260/181405713-47bb9619-1354-4c6d-aedc-2065c12932d5.png)

- VGGNet define

![image](https://user-images.githubusercontent.com/104436260/181405996-2e82b503-8127-4315-ac54-780a09e8950b.png)

-먼저 VGGnet이라는 이름으로 Class 생성

-VGG11 ,VGG13, VGG16, VGG19 모델 구조 딕셔너리로 define

-Convolution층 create_conv_laters함수 활용하여 정의

-Fully Connected layer define

-forward 층에서 모델 직접 학습

-create_conv_laters define-> VGG.types받아서 숫자면 convolution->batch->activation M이면 Maxpooling진행

- VGG16 Models define

![image](https://user-images.githubusercontent.com/104436260/181408086-95d689c7-c49f-4cfd-a4d3-38bf9c46966d.png)
![image](https://user-images.githubusercontent.com/104436260/181422669-a95f4fb6-88b7-4ba2-9304-a5ec254a0f60.png)
![image](https://user-images.githubusercontent.com/104436260/181422701-57dd2a3a-8956-4af9-89e3-2cf92fe7258f.png)
