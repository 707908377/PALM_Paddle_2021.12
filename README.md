# 标题：飞桨常规赛：PALM眼底彩照中黄斑中央凹定位 - 12月第3名方案
本项目对resnet152预训练模型进行训练，并自定义损失函数等，最终Score＝0.01409。

本项目AI Studio地址：https://aistudio.baidu.com/aistudio/projectdetail/3372077?contributionType=1
从中可以获得更加详细的介绍和可一键复现的飞桨算法代码
![image](https://user-images.githubusercontent.com/95835850/150338408-f0e09557-a7e8-4e54-b054-71845dca66f1.png)


## 提交时所使用的checkpoint
最终比赛提交的结果中，checkpoints使用的是/home/aistudio/work/lup/路径下的final

## 调优过程
本次比赛结果的调优过程：设定了401轮迭代（从epoch1到epoch401）

批次大小Batch_size设定为32，根据自己的显存大小进行设定

因为计算机字符都是以2的指数次幂进行存储的，所以设置 batch_size时尽量选择例如 4， 8， 16， 32， 64， 128， 256 等

Batch Size的大小影响模型的优化程度和速度。同时其直接影响到GPU内存的使用情况，假如你GPU内存不大，该数值最好设置小一点

使用 cosine annealing 的策略来动态调整学习率，learning_rate为1e-5

经测试以上参数设定可以达到较好的结果

## 总结与展望
进一步调整学习率及超参数

尝试其他优化器

尝试定义更深层的神经网络

模型能力有限度，尝试新的网络模型

丰富数据增强操作
