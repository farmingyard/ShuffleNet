# ShuffleNet
This is caffe implementation of ShuffleNet, For details, please read the original paper:  
["ShuffleNet: An Extremely Efficient Convolutional
Neural Network for Mobile Devices" by Xiangyu Zhang et. al. 2017](https://arxiv.org/pdf/1707.01083.pdf).
This code is based on camel007's implementation(https://github.com/camel007/Caffe-ShuffleNet), but I recode the cuda file for acceleration.

## How to use?
#### caffe.proto:
```
message LayerParameter {
...
optional ShuffleChannelParameter shuffle_channel_param = 164;
...
}
...
message ShuffleChannelParameter {
  optional uint32 group = 1[default = 1]; // The number of group
}
```

# Pretrained ShuffleNet 1x group=3 model on ImageNet
The top-1/5 accuracy rates by using single center crop (crop size: 224x224, image size: 256x256):

Network|Top-1|Top-5|Download|Architecture
:---:|:---:|:---:|:---:|:---:
MobileNet| 62.8%| 84.7%| [caffemodel (7.0 MB)](http://pan.baidu.com/s/1c2NBXOc)| [deploy](https://github.com/farmingyard/ShuffleNet/blob/master/shufflenet_1x_g3_deploy.prototxt)
