Week 2 quiz 3 Octave/Matlab Tutorial

notes: [机器学习笔记6 —— Matlab编程基础 - 知乎](https://zhuanlan.zhihu.com/p/32300438)


1\. Question 1
--------------

Suppose I first execute the following Octave/Matlab commands:


A = [1 2; 3 4; 5 6];

B = [1 2 3; 4 5 6];

Which of the following are then valid commands? Check all that apply. (Hint: A' denotes the transpose of A.)

C = A * B;
C = B * A;


1\. Question 3
--------------
Let AA be a 10x10 matrix andxx be a 10-element vector. Your friend wants to compute the product AxAx and writes the following code:

v = zeros(10, 1);

for i = 1:10

  for j = 1:10

    v(i) = v(i) + A(i, j) * x(j);

  end

end

How would you vectorize this code to run without any for loops? Check all that apply.

v = A * x;


1\. Question 4
--------------

Say you have two column vectors vv and ww, each with 7 elements (i.e., they have dimensions 7x1). Consider the following code:

z = 0;

for i = 1:7

  z = z + v(i) * w(i)

end

Which of the following vectorizations correctly compute z? Check all that apply.

这个程序无非就是两个7 x 1 的向量一个倒置跟另一个相乘，最后变成一个1 x 1的数。这里要注意倒置的顺序，不能将其变成7 x 7。

z = sum (v .* w);
z = w' * v;



1\. Question 5
--------------

In Octave/Matlab, many functions work on single numbers, vectors, and matrices. For example, the sin function when applied to a matrix will return a new matrix with the sin of each element. But you have to be careful, as certain functions have different behavior. Suppose you have an 7x7 matrix XX. You want to compute the log of every element, the square of every element, add 1 to every element, and divide every element by 4. You will store the results in four matrices, A, B, C, DA,B,C,D. One way to do so is the following code:





for i = 1:7
  for j = 1:7
    A(i, j) = log(X(i, j));
    B(i, j) = X(i, j) ^ 2;
    C(i, j) = X(i, j) + 1;
    D(i, j) = X(i, j) / 4;
  end
end


C = X + 1;

D = X / 4;

B = X .^ 2; => no 

B = X ^ 2;

点乘，就是矩阵里面每一个数字分别进行平方。
ex: 
X=[1,2,3;4,5,6;7,8,9]
for i = 1:3
  for j = 1:3
    B(i, j) = X(i, j) ^ 2;
  end;
end;

B =
     1     4     9
    16    25    36
    49    64    81
    
C = X + 1;
D = X / 4;
B = X .^ 2;

    

