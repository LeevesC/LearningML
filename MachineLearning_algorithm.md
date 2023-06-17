# Machine Learning Algorithm
Command+Shift+v open view window in VScode


## Linear Regression
### **General Conception**
> Loan credit limit is associated with age($x_1$) and income($x_2$). The coefficient of age is $\theta_1$, for income is $\theta_2$.

Fitting plane: $h_\theta(x)=\theta_0+\theta_1x_1+\theta_2x_2$

Multi variables: $h_\theta(x)=\sum^n_{i=0}\theta_ix_i=\theta^Tx$

### **Error**
The difference between the actual values and the predicted values: $\varepsilon$

For each sample(actual values): $y^{(i)}=\theta^Tx^{(i)}+\varepsilon^{(i)}$

> **Probabilistic perspective**  
> Each sample data is independent of each other.  
> Normal distribution with mean value is 0.

Function of Normal distribution
$$P(\varepsilon^{(i)})=\frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}(\mu=0)$$

Subtitute $y^{(i)}$ into $P(\varepsilon^{(i)})$, we get:
$$P(y^{(i)}|x^{(i)}; \theta)=\frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(y^{(i)}-\theta^Tx^{(i)})^2}{2\sigma^2}}$$  
To find a $\theta$ and $x$ make the result more close to actual value $y$, in other words the higher the probability, the better. 

Likelihood function:
$$L(\theta)=\prod_{i=1}^mp(y^{(i)}|x^{(i)}; \theta)=\prod_{i=1}^m\frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(y^{(i)}-\theta^Tx^{(i)})^2}{2\sigma^2}}$$
What kind of $\theta$ can make the output is actual value. We do not care what the exactly value of $L(\theta)$, instead which $\theta$ makes the formula maximum.  

Cost function:
$$J(\theta)=\frac{1}{2}\sum^m_{i=1}(y^{(i)}-\theta^Tx^{(i)})^2$$
After calculationg, we get cost function like above, the purpose is find a $\theta$ makes the cost function minimum.  

<mark>**Least squares method:**</mark>
$$J(\theta)=\frac{1}{2}(h_{\theta}(x^{(i)})-y^{(i)})^2=\frac{1}{2}(X\theta-y)^T(X\theta-y)$$
Using derivative to find its minimum value.
$$\frac{\partial J(\theta)}{\partial \theta}=...=X^TX\theta-X^Ty$$
 Therefore, partial derivative is 0, $\theta=(X^TX)^{-1}X^Ty$

<mark>**Gradient descent method:**</mark>  
purpose function:
$$J(\theta)=\frac{1}{2m}\sum^m_{i=1}(y^{(i)}-h_{\theta}(x^{(i)}))^2$$
- Find the appropriate direction at current position.
- Walking forward a small step along the direction above
- Loop the above two steps again and again untill reach the minimum.  

**Batch Gradient Descent**
$$\frac{\partial J(\theta)}{\partial \theta_j}=-\frac{1}{m}\sum^m_{i=1}(y^{(i)}-h_{\theta}(x^{(i)}))x_j^{i}$$
>update $\theta_j=\theta_j-\frac{\partial J(\theta)}{\partial \theta_j}$

**Stochastic Gradient Descent**  
>Using one sample stochastically for each descent step  

**Mini Batch Gradient Descent**
$$\theta_j=\theta_j-\alpha\frac{1}{10}\sum^{i+9}_{k=i}(y^{(k)}-h_{\theta}(x^{(k)}))x_j^{k}$$
>Using 10 sample for each descent step.