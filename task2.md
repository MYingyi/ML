

### 理解偏差和方差

- 机器学习的误差来自两方面，bias and variance

针对以上两种不同的方法，选择适当的方法，对具体的误差进行改进。

- 学习误差为什么是偏差和方差而产生的，并且推导数学公式

  对于样本而言，对其的研究用来拟合总体的分布情况。

  假设样本samples如下: {$x^1,x^2,...,x^n$}

  根据中心极限定理和大数定律，样本均值不一定等于总体均值，而样本均值的期望是等于样本均值的，即无偏性估计；然而样本方差的期望是小于总体的方差的，即:$E[s^2] = \frac{N-1}{N}\sigma ^2\neq \sigma ^2$

  也就是对均值和方差的学习。简单的模型受不同的数据影响较小（如:y=c(c为常数)），模型所覆盖的范围（拟合函数所在的空间）小

###  过拟合，欠拟合，

- 分别对应bias和variance什么情况

  过拟合对应于训练集上表现效果好（误差小），而测试机上效果表现不好（误差大）的情况，模型很好的拟合了训练集，这是方差高的表现。

  解决办法：1. 更多的训练数据 2.正则化，降低模型复杂程度

  欠拟合的表现是在训练集上，模型效果就不好的情况，即偏差高。

  解决办法：1. 增加特征，做特征衍生  2. 增加模型的复杂程度

  一般做交叉验证，是正确的数据竞赛过程，因为参赛者无法决定test data，所以要尽可能构造不同的验证集进行模拟测试。

- 学习鞍点，复习上次任务学习的全局最优和局部最优

  

  ### 梯度下降

- 学习Mini-Batch与SGD

  小批量：批和随机的折中

  一个随机

- 学习Batch与Mini-Batch，SGD梯度下降的区别

- 如何根据样本大小选择哪个梯度下降(批量梯度下降，Mini-Batch）

- 写出SGD和Mini-Batch的代码

- 梯度下降之三个小技巧：

  Tip1:调整学习率

  Tip2: SGD

  Tip3: feature scaling

  (详细解读后期补上)



- 学习回归模型评价指标

  均方误差，交叉熵等

  **以下是边听边记录的，这几天有事，没来得及总结，过几天及时补上**

![1557902905276](C:\Users\Mying\AppData\Roaming\Typora\typora-user-images\1557902905276.png)





![1557903103759](C:\Users\Mying\AppData\Roaming\Typora\typora-user-images\1557903103759.png)







![1557904240436](C:\Users\Mying\AppData\Roaming\Typora\typora-user-images\1557904240436.png)



![1557916000570](C:\Users\Mying\AppData\Roaming\Typora\typora-user-images\1557916000570.png)



![1557917275200](C:\Users\Mying\AppData\Roaming\Typora\typora-user-images\1557917275200.png)



