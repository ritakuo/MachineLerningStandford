# quiz - Logistic regression
1. 
Suppose that you have trained a logistic regression classifier, and it outputs on a new example xx a prediction hθ(x) = 0.4. This means (check all that apply):

Our estimate for P(y=1∣x;θ) is 0.4.
Our estimate for P(y=0∣x;θ) is 0.6.


2 [![Screen-Shot-2018-12-30-at-11-51-35-PM.png](https://i.postimg.cc/0j2mkds0/Screen-Shot-2018-12-30-at-11-51-35-PM.png)](https://postimg.cc/mzJhV9hP)

[![Screen-Shot-2018-12-30-at-11-52-37-PM.png](https://i.postimg.cc/90n4c61c/Screen-Shot-2018-12-30-at-11-52-37-PM.png)](https://postimg.cc/N2RG4PWn)
- Adding polynomial features (e.g., instead using h(x)=g(0+1x1+2x2+3x12+4x1x2+5x22) ) could increase how well we can fit the training data.
TRUE Adding new features can only improve the fit on the training set: since settingθ3=θ4=θ5=0 makes the hypothesis the same as the original one, gradient descent will use those features (by making the correspondingθj non-zero) only if doing so improves the training set fit.
- The positive and negative examples cannot be separated using a straight line. So, gradient descent will fail to converge. 
FALSE While it is true they cannot be separated, gradient descent will still converge to the optimal fit. Some examples will remain misclassified at the optimum.

- At the optimal value ofθ (e.g., found by fminunc), we will haveJ(θ)≥0 .
TRUE The cost functionJ(θ) is always non-negative for logistic regression.

- Because the positive and negative examples cannot be separated using a straight line, linear regression will perform as well as logistic regression on this data. 
FALSE While it is true they cannot be separated, logistic regression will outperform linear regression since its cost function focuses on classification, not prediction.

- J(θ) will be a convex function, so gradient descent should converge to the global minimum.
true
[![Screen-Shot-2018-12-31-at-12-28-43-AM.png](https://i.postimg.cc/MTBGR97Y/Screen-Shot-2018-12-31-at-12-28-43-AM.png)](https://postimg.cc/ygVBCXrJ)


4. Which of the following statements are true? Check all that apply.

CORRECT The sigmoid function g(z)=11+e−z is never greater than one (>1).

CORRECT The cost function J(θ) for logistic regression trained with m≥1 examples is always greater than or equal to zero.

For logistic regression, sometimes gradient descent will converge to a local minimum (and fail to find the global minimum). This is the reason we prefer more advanced optimization algorithms such as fminunc (conjugate gradient/BFGS/L-BFGS/etc).

WRONG Linear regression always works well for classification if you classify by using a threshold on the prediction made by linear regression.

%-----------------------%

CORRECT The one-vs-all technique allows you to use logistic regression for problems in which each y(i) comes from a fixed, discrete set of values.


CORRECT The cost function J(θ) for logistic regression trained with m≥1 examples is always greater than or equal to zero.

Since we train one classifier when there are two classes, we train two classifiers when there are three classes (and we do one-vs-all classification).


5. 
[![Screen-Shot-2018-12-31-at-12-39-26-AM.png](https://i.postimg.cc/9M2GDwTz/Screen-Shot-2018-12-31-at-12-39-26-AM.png)](https://postimg.cc/zLdLMBx1)

[![Screen-Shot-2018-12-31-at-12-41-00-AM.png](https://i.postimg.cc/3Jz0yDQ7/Screen-Shot-2018-12-31-at-12-41-00-AM.png)](https://postimg.cc/rKCw3spY)

htheta(x) = g(theta_0 + theta_1*x1 + theta_2*x2)
                -6         0         1

theta= [ -6
          0
          1]
preditct y=1. if -6 + x2>=0  => x2 >=6
so, we transition from negative to postive when x2 go from below 6 to above 6

