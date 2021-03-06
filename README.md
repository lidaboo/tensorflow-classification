# tensorflow-classification

Different neural network architechtures implemented in tensorflow for image classification. Weights converted from caffemodels. Some weights were converted using `misc/convert.py` others using [caffe-tensorflow](https://github.com/ethereon/caffe-tensorflow). The weights can be downloaded from [here](https://www.dropbox.com/sh/qpuqj03gv00ba85/AAApqsIe4SqSOrsfpwrYjOema?dl=0). Tested with Tensorflow 1.0. Weights for inception-V3 taken from Keras implementation provided [here](https://github.com/fchollet/deep-learning-models/blob/master/inception_v3.py). Contributions are welcome!

## Features

* A single call program to classify images using different architechtures (vgg-f, caffenet, vgg-16, vgg-19, googlenet, resnet-50, resnet-152, inception-V3)
* Returns networks as a dictionary of layers, so accessing activations at intermediate layers is easy
* Functions to classify single image or evaluate on whole validation set

## Usage

* For classification of a single image, `python classify.py --network 'resnet152' --img_path 'misc/sample.jpg'`
* For evaluation over whole ilsvrc validation set `python classify.py --network 'resnet152' --img_list '<list with image names>' --gt_labels '<list with gt labels corresponding to images>'`
* Currently the `--network` argument can take vggf, caffenet, vgg16, vgg19, googlenet, resnet50, resnet152, inceptionv3.

## Performance
These converted models have the following performance on the ilsvrc validation set, with each image resized to 224x224 (227 or 299 depending on architechture), and per channel mean subtraction.

| Network        | Top-1 Accuracy           | Top-5 Accuracy  |
| ------------- |:-------------:| :-----:|
| VGG-F      | 53.43% | 77.43% |
| CaffeNet      | 56.02% | 79.42% |
| VGG-16      | 65.77%      |   86.65% |
| VGG-19      | 66.14%      |   86.97% |
| GoogLeNet | 67.92%      |    88.29% |
| ResNet-50 | 70.65% |    89.85% |
| ResNet-152 | 72.64% |    90.92% |
| Inception-V3 | 76.85% |    93.39% |