# Week 2 Quiz 2 Linear Regression with Multiple Variables
=========================================


1\. Question 1
--------------

Suppose *m*=4 students have taken some class, and the class had a midterm exam and a final exam. You have collected a dataset of their scores on the two exams, which is as follows:

| midterm exam | (midterm exam)^22 | final exam |
| 89 | 7921 | 96 |
| 72 | 5184 | 74 |
| 94 | 8836 | 87 |
| 69 | 4761 | 78 |

[![Screen-Shot-2018-12-12-at-4-04-29-AM.png](https://i.postimg.cc/XYw6nw5q/Screen-Shot-2018-12-12-at-4-04-29-AM.png)](https://postimg.cc/sMDNcGwC)


ans: 

x1(3) -> 94
normalize feature x-u /s  where u is avg of x and 
s = max- min = 94-69 = 25

94 - 81 / 25 = 0.52


2\. Question 2
--------------

[![Screen-Shot-2018-12-12-at-4-05-38-AM.png](https://i.postimg.cc/pdcHSP8J/Screen-Shot-2018-12-12-at-4-05-38-AM.png)](https://postimg.cc/xkmhJD6X)

- You find that the value of J(θ)  decreases slowly and is still decreasing after 15 iterations.
=> Rather than use the current value of α , it'd be more promising to try a larger value of α (say α=1.0 ).

- You find that the value of J(θ) decreases quickly then levels of
=> We want gradient descent to quickly converge to the minimum, so the current setting of α seems to be good

- you find that the value of J(θ) increases over time.
=> Rather than use the current value of \alphaα, it'd be more promising to try a smaller value of \alphaα (say \alpha = 0.1α=0.1).



3\. Question 3
--------------

[![Screen-Shot-2018-12-12-at-4-07-14-AM.png](https://i.postimg.cc/K8YpHB5C/Screen-Shot-2018-12-12-at-4-07-14-AM.png)](https://postimg.cc/nC61ssg1)


X has m rows and n + 1 columns (+1 because of the x0=1 term. y is an m-vector. θ is an (n+1)-vector.

point

4\. Question 4
--------------

Suppose you have a dataset with m = 50m=50 examples and n = 200000n=200000 features for each example. You want to use multivariate linear regression to fit the parameters \thetaθ to our data. Should you prefer gradient descent or the normal equation?

if n >> m, then gradient descent

 m=50 examples and n=15 => The normal equation, since it provides an efficient way to directly find the solution



5\. Question 5
--------------

Which of the following are reasons for using feature scaling?

=> It speeds up gradient descent by making it require fewer iterations to get to a good solution

