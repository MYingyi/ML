### 李宏毅机器学习笔记p1-p2

- 了解什么是Machine learning

  仅靠传统的人工规则，机器并不能具有智能。机器学习的本质是找到一个函数y=f(x);

  包括三个过程：函数集合->评价函数的函数(损失函数)->选择最好的函数

  ![](C:\Users\Mying\Desktop\微信图片_20190512141705.png)

- 学习中心极限定理，学习正态分布，学习最大似然估计

- 推导回归Loss function

  线性回归（以梦可宝变身为例）
  $$
  y = b + \sum w_ix_i
  $$
  回归问题，平方误差，绝对值误差等可以作为损失函数。（衡量预测与真值之间的差值 how bad the model is）
  $$
  w^*,b^* = argminL(f)
  $$

- 学习损失函数与凸函数之间的关系，了解全局最优和局部最优

  凸函数，任意两点之间的线性组合大于对应的y,具有全局最优解

- 学习导数，泰勒展开
  $$
  P(x)=f\left(x_{0}\right)+f^{\prime}\left(x_{0}\right)\left(x-x_{0}\right)+\frac{f^{(2)}\left(x_{0}\right)}{2 !}\left(x-x_{0}\right)^{2}+\cdots+\frac{f^{(n)}\left(x_{0}\right)}{n !}\left(x-x_{0}\right)^{n}
  $$
  

- 推导梯度下降公式
  $$
  w_{k} \rightarrow w_{k}^{\prime}=w_{k}-\eta \frac{\partial L}{\partial w_{k}}
  $$

  $$
  b_{l} \rightarrow b_{l}^{\prime}=b_{l}-\eta \frac{\partial L}{\partial b_{l}}
  $$

  

- 写出梯度下降的代码

  ```python
  #梯度下降法实现
  # numpy实现
  import numpy as np
  x = np.array([1,2,3])
  y = np.array([2,4,6])
  
  epoches = 10
  lr = 0.1
  w = 0
  cost=[]
  
  for epoch in range(epoches):
      yhat = x*w
      loss = np.average((yhat-y)**2)
      cost.append(loss)
      dw = -2*(y-yhat)@ x.T/(x.shape[0])
      w=w-lr*dw
      print(w)
  ```

- 学习L2-Norm，L1-Norm，L0-Norm
  $$
  +\lambda \sum w_i^2
  $$
  

  为了防止过拟合，对参数进行正则化。将正则化项加入到损失函数中一起优化，约束参数取值不要过大。

   **L0范数是指向量中非0的元素的个数**。如果我们用L0范数来规则化一个参数矩阵W的话，就是希望W的大部分元素都是0。换句话说，让参数W是稀疏的。

  **L1范数是指向量中各个元素绝对值之和**。L1适用于特征选择，可解释性。

  **L2范数是指向量各元素的平方和然后求平方根**。我们让L2范数的规则项||W||2最小，可以使得W的每个元素都很小，都接近于0,平滑，平滑的function对异常值不敏感，但不能平滑成一条水平线，$\lambda$越大，越考虑$w$。

  L1会趋向于产生少量的特征，而其他的特征都是0，而L2会选择更多的特征，这些特征都会接近于0。

  


  ![这里写图片描述](https://img-blog.csdn.net/20180621090405436?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3JlZF9zdG9uZTE=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

- 推导正则化公式

  ```python
  # L1,L2,elastic-net正则化
  def l1_normal(x):
      return torch.abs(x).sum()
  def l2_normal(x):
      return torch.pow(x,2).sum()
  def elastic_net(x,a,b):
      return l1_normal(x)*a+l2_normal(x)*b
  ```

  

- 说明为什么用L1-Norm代替L0-Norm

  L1范数是L0范数的最优凸近似。任何的规则化算子，如果他在Wi=0的地方不可微，并且可以分解为一个“求和”的形式，那么这个规则化算子就可以实现稀疏。W的L1范数是绝对值，|w|在w=0处是不可微。 虽然L0可以实现稀疏，但是实际中会使用L1取代L0。因为L0范数很难优化求解，L1范数是L0范数的最优凸近似，它比L0范数要容易优化求解。

- 学习为什么只对w/Θ做限制，不对b做限制

  因为b影响的式整体的平移，并不影响函数拟合的程度及模型的复杂性。

- 隐藏特征的探索

  

  



