### Segmentation 项目结果说明

- Train.py		 	实现的fcn8的代码
- convert_fcn_dataset.py	实现了准备数据集的代码
- Segmentation-log.png		Tinymind 运行时的log 截图
- /output/eval              Train过程中产生的验证图片
- Local TF Record.png       本地生成的TF Record的截图



### 实现fcn-8s的心得体会
1. 关于作业的实现
> 在train.py中，老师已经为我们实现好了 fcn-16s
> 而fcn-16s与 fcn-8s的主要区别是，多了一个x2的上采样
> 并且将pool3的结果进行1x1卷积后，与上一步上采样的结果进行相加，然后把x16的反卷积改成x8的反卷积
> 一开始的时候没有理解作业的要求，后来仔细研读了论文，有个图非常的清晰明了
2. 关于对fcn-8s的理解
> fcn-8s为什么能比 fcn-16s取得更精确的结果，是因为拿到了pool3层更细节更密集的输入结果
> 也有点像残差网络的结构，跳层的去将更前面层的feature map 作为输入，可以获得更细节的更与原图片接近的feature maps

