# Machine Learning Algorithm
Command+Shift+v open view window in VScode


## Linear Regression
### **General Conception**
Loan credit limit is associated with age($x_1$) and income($x_2$). The coefficient of age is $\theta_1$, for income is $\theta_2$.

Fitting plane: $h_\theta(x)=\theta_0+\theta_1x_1+\theta_2x_2$

Multi variables: $h_\theta(x)=\sum^n_{i=0}\theta_ix_i=\theta^Tx$

### **Error**
The difference between the actual values and the predicted values: $\varepsilon$

For each sample(actual values): $y^{(i)}=\theta^Tx^{(i)}+\varepsilon^{(i)}$