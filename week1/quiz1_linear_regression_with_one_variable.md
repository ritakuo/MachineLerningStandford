# quiz 1 

Linear Regression with One Variable
===================================


1\. Question 1
--------------

Consider the problem of predicting how well a student does in her second year of college/university, given how well she did in her first year.

Specifically, let x be equal to the number of "A" grades (including A-. A and A+ grades) that a student receives in their first year of college (freshmen year). We would like to predict the value of y, which we define as the number of "A" grades they get in their second year (sophomore year).

Here each row is one training example. Recall that in linear regression, our hypothesis is hθ(x)=θ0+θ1x, and we use mm to denote the number of training examples.

![](https://d396qusza40orc.cloudfront.net/flex-ml/quizIIq1v3.png)

For the training set given above (note that this training set may also be referenced in other questions in this quiz), what is the value of mm? In the box below, please enter your answer (which should be a number between 0 and 10).

ans:
4


2\. Question 2
--------------

For this question, assume that we are

using the training set from Q1. Recall our definition of the

cost function was
[![Screen-Shot-2018-12-10-at-10-59-45-PM.png](https://i.postimg.cc/3xK7HCdS/Screen-Shot-2018-12-10-at-10-59-45-PM.png)](https://postimg.cc/cr5PR37w)


What is J(0, 1)J(0,1)?

-4^2 + -4^2 + -1 ^2 + -3^2  / 2 *4 = 16 + 16+ 1 + 9 /8 =  5.25


3\. Question 3
--------------
Suppose we set θ0=−1,θ1=0.5. What is hθ(4)?

Answer: 

Setting x = 4, we have hθ(x)=θ0+θ1x = -1 + (0.5)(4) = 1


4\. Question 4
--------------

In the given figure, the cost function J(\theta_0,\theta_1)J(θ0​,θ1​) has been plotted against \theta_0θ0​ and \theta_1θ1​, as shown in 'Plot 2'. The contour plot for the same cost function is given in 'Plot 1'. Based on the figure, choose the correct options (check all that apply).

![](https://d396qusza40orc.cloudfront.net/ml/images/4.2-quiz-1.png)

If we start from point B, gradient descent with a well-chosen learning rate will eventually help us reach at or near point A, as the value of cost function J(\theta_0,\theta_1)J(θ0​,θ1​) is minimum at A.

Point P (the global minimum of plot 2) corresponds to point A of Plot 1.

5\. Question 5
--------------

uppose that for some linear regression problem (say, predicting housing prices as in the lecture), we have some training set, and for our training set we managed to find some θ<sub>0</sub>, θ<sub>1</sub> such that J(θ<sub>0</sub>,θ<sub>1</sub>)=0.

Which of the statements below must then be true? (Check all that apply.)

* For this to be true, we must have y<sup>(i)</sup>=0 for every value of i=1,2,…,m.

* Gradient descent is likely to get stuck at a local minimum and fail to find the global minimum.

* For this to be true, we must have θ<sub>0</sub>=0 and θ<sub>1</sub>=0 so that h<sub>θ</sub>(x)=0

* Our training set can be fit perfectly by a straight line, i.e., all of our training examples lie perfectly on some straight line.

Answers: </br>

True or False | Statement | Explanation 
--- | --- | ---
False | For this to be true, we must have y<sup>(i)</sup>=0 for every value of i=1,2,…,m. | So long as all of our training examples lie on a straight line, we will be able to find θ<sub>0</sub> and θ<sub>1</sub>) so that J(θ<sub>0</sub>,θ<sub>1</sub>)=0. It is not necessary that y<sup>(i)</sup> for all our examples. 
False | Gradient descent is likely to get stuck at a local minimum and fail to find the global minimum. | none
False | For this to be true, we must have θ<sub>0</sub>=0 and θ<sub>1</sub>=0 so that h<sub>θ</sub>(x)=0 | If J(θ<sub>0</sub>,θ<sub>1</sub>)=0 that means the line defined by the equation "y = θ<sub>0</sub> + θ<sub>1</sub>x" perfectly fits all of our data. There's no particular reason to expect that the values of θ<sub>0</sub> and θ<sub>1</sub> that achieve this are both 0 (unless y<sup>(i)</sup>=0 for all of our training examples).
True | Our training set can be fit perfectly by a straight line, i.e., all of our training examples lie perfectly on some straight line. | None

Other Options: </br>

True or False | Statement | Explanation 
--- | --- | ---
False | We can perfectly predict the value of y even for new examples that we have not yet seen. (e.g., we can perfectly predict prices of even new houses that we have not yet seen.)  | None
False | This is not possible: By the definition of J(θ<sub>0</sub>,θ<sub>1</sub>), it is not possible for there to exist θ<sub>0</sub> and θ<sub>1</sub> so that J(θ<sub>0</sub>,θ<sub>1</sub>)=0 | None
True | For these values of θ<sub>0</sub> and θ<sub>1</sub> that satisfy J(θ<sub>0</sub>,θ<sub>1</sub>)=0, we have that h<sub>θ</sub>(x<sup>(i)</sup>)=y<sup>(i)</sup> for every training example (x<sup>(i)</sup>,y<sup>(i)</sup>) | None