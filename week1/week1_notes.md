# week 1 Notes

## Supervised learning,
- given a data set and already know what our correct output should look like, having the idea that there is a relationship between the input and the output.
### Classification v.s. regression
- Regression
  - predict results within a continuous output, meaning that we are trying to map input variables to some continuous function. 
    - ex: Given data about the size of houses on the real estate market, try to predict their price. Price as a function of size is a continuous output, so this is a regression problem.
    - ex: Given a picture of a person, we have to predict their age on the basis of the given picture
- classfication
  - trying to predict results in a discrete output. In other words, we are trying to map input variables into discrete categories.
    - ex: whether the house "sells for more or less than the asking price." Here we are classifying the houses based on price into two discrete categories
    - ex: Given a patient with a tumor, we have to predict whether the tumor is malignant or benign.

Example 1:

Given data about the size of houses on the real estate market, try to predict their price. Price as a function of size is a continuous output, so this is a regression problem.

We could turn this example into a classification problem by instead making our output about whether the house "sells for more or less than the asking price." Here we are classifying the houses based on price into two discrete categories.

Example 2:

(a) Regression - Given a picture of a person, we have to predict their age on the basis of the given picture

(b) Classification - Given a patient with a tumor, we have to predict whether the tumor is malignant or benign.

## unsupervised learning

- approach problems with little or no idea what our results should look like. We can derive this structure by clustering the data based on relationships among the variables in the data.

- With unsupervised learning there is no feedback based on the prediction results.

Example:

Clustering: Take a collection of 1,000,000 different genes, and find a way to automatically group these genes into groups that are somehow similar or related by different variables, such as lifespan, location, roles, and so on.

Non-clustering: The "Cocktail Party Algorithm", allows you to find structure in a chaotic environment. (i.e. identifying individual voices and music from a mesh of sounds at a cocktail party).


## cost function
Measure the accuracy of our hypothesis function by using a cost function. This takes an average difference (actually a fancier version of an average) of all the results of the hypothesis with inputs from x's and the actual output y's

[![Screen-Shot-2018-12-17-at-11-25-25-PM.png](https://i.postimg.cc/T2tGV83R/Screen-Shot-2018-12-17-at-11-25-25-PM.png)](https://postimg.cc/NL2WtzXV)

[![Screen-Shot-2018-12-17-at-11-26-17-PM.png](https://i.postimg.cc/ncwDww0x/Screen-Shot-2018-12-17-at-11-26-17-PM.png)](https://postimg.cc/gn8jxsCt)

## gradient descent
So we have our hypothesis function and we have a way of measuring how well it fits into the data. Now we need to estimate the parameters in the hypothesis function

[![Screen-Shot-2018-12-17-at-11-32-13-PM.png](https://i.postimg.cc/7h5mpT8Y/Screen-Shot-2018-12-17-at-11-32-13-PM.png)](https://postimg.cc/n9t4mrh6)

[![Screen-Shot-2018-12-17-at-11-35-50-PM.png](https://i.postimg.cc/fysYvtzr/Screen-Shot-2018-12-17-at-11-35-50-PM.png)](https://postimg.cc/k6jVJ5tQ)
## Gradient Descent For Linear Regression

[![Screen-Shot-2018-12-17-at-11-37-57-PM.png](https://i.postimg.cc/6QN6qdYg/Screen-Shot-2018-12-17-at-11-37-57-PM.png)](https://postimg.cc/qNjHZCfx)

## linear algebra

[![Screen-Shot-2018-12-15-at-2-27-52-PM.png](https://i.postimg.cc/5tF7kRvK/Screen-Shot-2018-12-15-at-2-27-52-PM.png)](https://postimg.cc/f3DfV58Y)

```
% The ; denotes we are going back to a new row.
A = [1, 2, 3; 4, 5, 6; 7, 8, 9; 10, 11, 12]

% Initialize a vector 
v = [1;2;3] 

% Get the dimension of the matrix A where m = rows and n = columns
[m,n] = size(A)

% You could also store it this way
dim_A = size(A)

% Get the dimension of the vector v 
dim_v = size(v)

% Now let's index into the 2nd row 3rd column of matrix A
A_23 = A(2,3)



```
[![Screen-Shot-2018-12-15-at-2-31-10-PM.png](https://i.postimg.cc/MHZYxPMS/Screen-Shot-2018-12-15-at-2-31-10-PM.png)](https://postimg.cc/DJDGPcPj)


## Inverse and Transpose
[![Screen-Shot-2018-12-15-at-2-34-58-PM.png](https://i.postimg.cc/NMn0fLLj/Screen-Shot-2018-12-15-at-2-34-58-PM.png)](https://postimg.cc/zbnNxzns)


[![Screen-Shot-2018-12-15-at-3-00-57-PM.png](https://i.postimg.cc/D0g5VVxF/Screen-Shot-2018-12-15-at-3-00-57-PM.png)](https://postimg.cc/0Kz7m4gH)

```
% Initialize matrix A 
A = [1,2,0;0,5,6;7,0,9]

A =

   1   2   0
   0   5   6
   7   0   9


% Transpose A 
A_trans = A'
` `
A_trans =

   1   0   7
   2   5   0
   0   6   9

% Take the inverse of A 
A_inv = inv(A)

A_inv =

   0.348837  -0.139535   0.093023
   0.325581   0.069767  -0.046512
  -0.271318   0.108527   0.038760


% What is A^(-1)*A? 
A_invA = inv(A)*A

A_invA =

   1.00000  -0.00000   0.00000
   0.00000   1.00000  -0.00000
  -0.00000   0.00000   1.00000



```

