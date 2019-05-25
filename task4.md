### task4学习打卡内容：

![1558794781120](https://github.com/MYingyi/ML/blob/d749566b16ada328e63c700d0e991f8a71aebd68/1558794781120.png)

由于时间关系，看完视频后，就不进行视频内容的复现了，结合自己的认识和学习，归纳如下：

- 从基础概率推导贝叶斯公式，朴素贝叶斯公式(1)

 P(A|B)=P(AB)/P(B)
 P(AB)=P(A|B)P(B)=P(B|A)P(A)  
$$
P(B | A)=\frac{P(A | B) P(B)}{P(A)}
$$
*P*(*C*1∣*x*) 是由贝叶斯（bayes）公式得到的；P(x)*P*(*x*) 是由全概率公式得到的

- 学习先验概率(2)

  先验概率是在缺乏某个事实的情况下描述一个变量;用频率占比来估计先验概率，是“由因求果”的体现。

- 学习后验概率(3)

  后验概率是在考虑了一个事实之后的条件概率. ，判断事情的发生是由哪一种原因引起的。是“由果求因”。

- 学习LR和linear regreeesion之间的区别(4)

  线性回归和逻辑回归之间：一个是解决回归问题，一个是解决分类问题；

  线性回归假设残差服从高斯分布，然后极大似然估计，进行最小二乘法计算；

  而逻辑回归是假设服从二项分布，对数极大似然估计，构造损失函数进行梯度下降求解。

  ![1558795157199](./ML/1558795157199.png)

  推导：

  ![1558795902306](C:\Users\Mying\AppData\Roaming\Typora\typora-user-images\1558795902306.png)

- 推导sigmoid function公式(5)

sigmoid函数与一个概率分布联系起来，那就是伯努利分布。

伯努利分布的概率质量函数为：

​             ![img](https://img-blog.csdn.net/20180320000139585?watermark/2/text/Ly9ibG9nLmNzZG4ubmV0L3UwMTI0MjE4NTI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

可以知道x=1时的概率为p，x=0时的概率为1-p，即$f(1|p) = p$，$f(0|p) = 1-p$

推导如下，其实就是多分类softmaxd的二分类应用：

![1558796350054](C:\Users\Mying\AppData\Roaming\Typora\typora-user-images\1558796350054.png)





