# rcf
variety of Richer Convolutional Features for Edge Detection (resnet101-based)

## motivation
原论文已经有一个[pytorch实现](https://github.com/meteorshowers/RCF-pytorch)，再次重复造轮子没有必要。

所以作为课程作业，同时想了解下edge-detection是怎么做的，所以试着照原论文的思想，将backbone换成resnet101，结构稍微做一些改变，测试一下效果。

许多处参照了[pytorch实现](https://github.com/meteorshowers/RCF-pytorch)， 如训练策略，网络实现，（data_loader直接拿来用了）。


## results
现在模型才训练了 2%  （10000/490000）， 以下是一些临时结果。
依次是layer1 ~ layer5的结果，综合结果， groundtruth，original image共8个图

<img src="examples/0-1.png" width="100" /><img src="examples/0-2.png" width="100" /><img src="examples/0-3.png" width="100" /><img src="examples/0-4.png" width="100" /><img src="examples/0-5.png" width="100" /><img src="examples/0-6.png" width="100" /><img src="examples/0-7.png" width="100" /><img src="examples/0-img.jpg" width="100" />

<img src="examples/1-1.png" width="100" /><img src="examples/1-2.png" width="100" /><img src="examples/1-3.png" width="100" /><img src="examples/1-4.png" width="100" /><img src="examples/1-5.png" width="100" /><img src="examples/1-6.png" width="100" /><img src="examples/1-7.png" width="100" /><img src="examples/1-img.jpg" width="100" />

<img src="examples/3-1.png" width="100" /><img src="examples/3-2.png" width="100" /><img src="examples/3-3.png" width="100" /><img src="examples/3-4.png" width="100" /><img src="examples/3-5.png" width="100" /><img src="examples/3-6.png" width="100" /><img src="examples/3-7.png" width="100" /><img src="examples/3-img.jpg" width="100" />

## requirements

* pytorch 0.4.1
* python 3.6.6
* dataset(provide by [original rcf repo](https://github.com/yun-liu/rcf))
    * http://mftp.mmcheng.net/liuyun/rcf/data/bsds_pascal_train_pair.lst
    * http://mftp.mmcheng.net/liuyun/rcf/data/HED-BSDS.tar.gz
    * http://mftp.mmcheng.net/liuyun/rcf/data/PASCAL.tar.gz
* and other requiremnts... (cv2, numpy , etc.)

## usage

#### train:

* put your data in 'data/HED-BSDS_PASCAL' (or make a soft link)
* python train.py

#### simple example:
* python example.py

#### evaluate:

it may take several hours...
* pretrained model will be available soon....
* require matlab
* [Structured Edge Detection Toolbox](https://github.com/pdollar/edges/)
* edgesEvalDir.m
