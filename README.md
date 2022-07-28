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



