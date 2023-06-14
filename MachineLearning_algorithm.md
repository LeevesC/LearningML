# Machine Learning Algorithm
Command+Shift+v open view window in VScode


## 线性回归
### 通俗理解
贷款额度与年龄($x_1$)和收入有关($x_2$)，年龄参数是$\theta_1$，收入参数是$\theta_2$。

拟合平面：$h_\theta(x)=\theta_0+\theta_1x_1+\theta_2x_2$

推广到多变量：$h_\theta(x)=\sum^n_{i=0}\theta_ix_i=\theta^Tx$

### 误差
真实值和预测值之间的差异为$\epsilon$

对于每一个样本(真实值)：$y^{(i)}=\theta^Tx^{(i)}+\epsilon^{(i)}$