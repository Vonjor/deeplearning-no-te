# 回归(Regression)

## 1、机器学习三部曲

step1：定义一个model即function set

step2：定义一个goodness of function即损失函数去评估该function的好坏

step3：寻找一个最好的function

## 2、线性回归模型

$$
y = b + \sum(w_ix_i)
$$

$$
x_i:特征值，b：偏置，w_i:权重
$$

## 3、损失函数

为了衡量function set中的某个function的好坏，我们需要一个评估函数，即Loss function，损失函数，简称`L`；Loss Function是一个function的function。
$$
L(f)=L(w,b)
$$
**即Loss Function可以衡量一组参数的好坏**
$$
L(f)=\sum_{n=1}^m(\widehat{y}_n-f(x_i^n))^2
$$

$$
L(w,b)=\sum_{n=1}^m(\widehat{y}_n-(b+wx_i^n))^2
$$

找出能使Loss值最小的w，b

## 4、梯度下降

分别计算w,b的偏导数，以w为例:(α为学习率)
$$
step1:随机选择一个w的初始值w_0
$$

$$
step2:计算\frac{dL}{dw}|_{w=w_0},更新w:w_1=w_0-\alpha\frac{dL}{dw}|_{w=w_0}
$$

$$
step3:计算\frac{dL}{dw}|_{w=w_1},更新w:w_2=w_1-\alpha\frac{dL}{dw}|_{w=w_1}
$$

$$
...
$$

## 5、正则化

正则化不考虑偏置b

正则化后的Loss Function为:
$$
L=\sum_{n=1}^m(\widehat{y}_n-(b+wx_i^n))^2+\lambda\sum(w_i)^2
$$

## 6、误差

模型的误差来自于偏置b和方差

- 欠拟合的loss主要来自偏差
- 过拟合的loss主要来自方差

随着模型复杂度的增加，来自偏置的误差逐渐减小，来自方差的误差逐渐变大，可观察的误差会先减小到极值，然后逐渐变大。