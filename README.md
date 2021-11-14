# pytorch-CIFAR10-Lenet5



### 1 Backround

This project is the first assignment of the artificial Intelligence security course of School of Software, Zhejiang University. It aims to use CIAR10 data set to train the convolutional neural network and study the influence of hyperparameters on the training process .

### 2 Homework requirement

your own deep neural network (in Pytorch,PaddlePaddle...).

Homework #1
Creating your own github account.  
Implementing your own deep neural network (in Pytorch,PaddlePaddle...).  
Training it on CIFAR10.  
Tuning a hyper-parameter and analyzing its effects on performance.  
Writing a README.md to report your findings.  



### 文件说明

dataset  （存放数据集压缩包cifar-10-python.tar.gz,需要手动下载该数据集并放到该文件夹中）

model  （存放模型）

drawpic （存放readme里的图片）



### 调参分析报告

**1、learning rate**

<img src=".\drawpic\Figure_lr.png" alt="Figure_lr" style="zoom: 80%;" />





在较慢于梯度下降的10倍（带进上式去算可得），通常可取0.5,0.9,0.99，情况一般的调整没有调整的那么重要适当取值即可。

**2、momentum**



<img src=".\drawpic\Figure_momentum.png" alt="Figure_momentum" style="zoom: 80%;" />

当![\公测](https://private.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20%5Cbeta)= 0.9时，最大速度相当于梯度下降的10倍（带进上式去算可得），通常![\公测](https://private.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20%5Cbeta)可取0.5,0.9,0.99，情况一般![\公测](https://private.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20%5Cbeta)的调整没有![\α](https://private.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20%5Calpha)调整的那么重要适当取值即可。



**3、batchsize**

<img src=".\drawpic\Figure_batchsize.png" alt="Figure_batchsize" style="zoom: 80%;" />

The momentum  

Batch_size is usually 2 to the n. Take 32 64 128 256... . The larger batch is, the acceleration effect of general model is obvious. Although the larger the batch size is, the faster the model runs, it does not mean that the bigger the batch size is, the better the effect is.  

 

When the batch size increases, the model training is more stable and the learning rate can be slightly increased. However, sometimes the impact of noise brought by the small batch size may make the model obtain better generalization ability and more easily pass the saddle point in the loss function (the loss function presents the illusion of reaching the minimum value in a certain direction at a certain point. In fact, in the other direction is the abyss, which is the randomness provided by Small Batch to help the model skip saddle points. Of course, the small batch size has the disadvantage of poor training stability.  

