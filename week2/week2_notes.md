# Week 2 notes

## MATLAB

- octave/MATLAB array indices start from one, not zero. If you're storting θ0 and θ1 in a vector called theta, the values will be theta(1) and
theta(2).

- If you are seeing many errors at runtime, inspect your matrix operations to make sure that you're adding and multiplying matrices of compat-ible dimensions. Printing the dimensions of variables with the size command will help you debug.


## Set data for linear regression

```
data = load('ex1data1.txt'); % read comma separated data

plot(x, y, 'rx', 'MarkerSize', 10); % Plot the data
ylabel('Profit in $10,000s'); % Set the y-axis label
xlabel('Population of City in 10,000s'); % Set the x􀀀axis label

X = data(:, 1); y = data(:, 2);
m = length(y); % number of training examples

%% ======================= Part 2: Plotting =======================
fprintf('Plotting Data ...\n')
data = load('ex1data1.txt');
X = data(:, 1); y = data(:, 2);
m = length(y); % number of training examples

% Plot Data
% Note: You have to complete the code in plotData.m
plotData(X, y);


```


## Multiple Features
[![Screen-Shot-2018-12-14-at-4-48-32-AM.png](https://i.postimg.cc/hPdQ361T/Screen-Shot-2018-12-14-at-4-48-32-AM.png)](https://postimg.cc/1fyz8WT3)

[![Screen-Shot-2018-12-14-at-4-51-54-AM.png](https://i.postimg.cc/B6P19zfr/Screen-Shot-2018-12-14-at-4-51-54-AM.png)](https://postimg.cc/vgMm53Bh)

[![Screen-Shot-2018-12-14-at-4-05-38-AM.png](https://i.postimg.cc/5yQ8ygXG/Screen-Shot-2018-12-14-at-4-05-38-AM.png)](https://postimg.cc/2Lm1X4FF)

[![Screen-Shot-2018-12-14-at-4-06-58-AM.png](https://i.postimg.cc/0N3YshQm/Screen-Shot-2018-12-14-at-4-06-58-AM.png)](https://postimg.cc/sBYQP65D)

## Gradient Descent for Multiple Variables

[![Screen-Shot-2018-12-14-at-11-50-25-PM.png](https://i.postimg.cc/s2dBbpmc/Screen-Shot-2018-12-14-at-11-50-25-PM.png)](https://postimg.cc/qNwM369h)


### implementation of  linear regression to minimize cost function

```

X = [ones(m,1),data(:,1)]; % initial parameters
theta = zeros(2,1) %θ0 intercept term
% Some gradient descent settings
interations= 1500;
alpha =0.01;

% compute and display initial cost
J = computeCost(X, y, theta);
fprintf('With theta = [0 ; 0]\nCost computed = %f\n', J);
fprintf('Expected cost value (approx) 32.07\n');

```

```
%computing the cost J(θ) / computeCost.m

function J = computeCost(X, y, theta)
%COMPUTECOST Compute cost for linear regression
%   J = COMPUTECOST(X, y, theta) computes the cost of using theta as the
%   parameter for linear regression to fit the data points in X and y

% Initialize some useful values
m = length(y); % number of training examples

% You need to return the following variables correctly 
J = 0;

% ====================== YOUR CODE HERE ======================
% Instructions: Compute the cost of a particular choice of theta
%               You should set J to the cost.
J = 1/(2*m) * sum((X*theta - y) .^ 2);

% =========================================================================

end



```

- parameters of the model are θj values, which will be adjusted to minimize cost of J(θ), by using batch gradient descent algorithm, where each interation will perform update. 
- with each step of gradient descent, your parameter θj come closer to optimal values that will achieve lowest cost J(θ)


[![Screen-Shot-2018-12-14-at-4-15-54-AM.png](https://i.postimg.cc/9f8D59Ln/Screen-Shot-2018-12-14-at-4-15-54-AM.png)](https://postimg.cc/R3tSwW57)

### implementation of gradient descent 
-  J(θ) is parameterized by vector θ. Minimize the value of J(θ) by changging the value of vector θ
- to verify gradient descent is working correctly, J(θ) will descrease with each step and converge to steady value

```
fprintf('\nRunning Gradient Descent ...\n')
% run gradient descent
theta = gradientDescent(X, y, theta, alpha, iterations);

% print theta to screen
fprintf('Theta found by gradient descent:\n');
fprintf('%f\n', theta);
fprintf('Expected theta values (approx)\n');
fprintf(' -3.6303\n  1.1664\n\n');

% Plot the linear fit
hold on; % keep previous plot visible
plot(X(:,2), X*theta, '-')
legend('Training data', 'Linear regression')
hold off % don't overlay any more plots on this figure

% Predict values for population sizes of 35,000 and 70,000
predict1 = [1, 3.5] *theta;
fprintf('For population = 35,000, we predict a profit of %f\n',...
    predict1*10000);
predict2 = [1, 7] * theta;
fprintf('For population = 70,000, we predict a profit of %f\n',...
    predict2*10000);

```


## Gradient Descent in Practice I - Feature Scaling
We can speed up gradient descent by having each of our input values in roughly the same range. This is because θ will descend quickly on small ranges and slowly on large ranges, and so will oscillate inefficiently down to the optimum when the variables are very uneven.

Two techniques to help with this are feature scaling and mean normalization. 
- Feature scaling involves dividing the input values by the range (i.e. the maximum value minus the minimum value) of the input variable, resulting in a new range of just 1. 
- Mean normalization involves subtracting the average value for an input variable from the values for that input variable resulting in a new average value for the input variable of just zero. 

To implement both of these techniques, adjust your input values as shown in this formula:

[![Screen-Shot-2018-12-14-at-4-19-40-AM.png](https://i.postimg.cc/MT6mt1v3/Screen-Shot-2018-12-14-at-4-19-40-AM.png)](https://postimg.cc/SXP9x2Lc)

## Gradient Descent in Practice II - Learning Rate

Debugging gradient descent. Make a plot with number of iterations on the x-axis. Now plot the cost function, J(θ) over the number of iterations of gradient descent. If J(θ) ever increases, then you probably need to decrease α.

Automatic convergence test. Declare convergence if J(θ) decreases by less than E in one iteration, where E is some small value such as 10−3. However in practice it's difficult to choose this threshold value.

[![Screen-Shot-2018-12-14-at-4-24-26-AM.png](https://i.postimg.cc/25RDqSVS/Screen-Shot-2018-12-14-at-4-24-26-AM.png)](https://postimg.cc/DSgDHFr9)

[![Screen-Shot-2018-12-14-at-4-25-33-AM.png](https://i.postimg.cc/8P234nDy/Screen-Shot-2018-12-14-at-4-25-33-AM.png)](https://postimg.cc/ppBqXCm8)

## Normal Equation
In the "Normal Equation" method, we will minimize J by explicitly taking its derivatives with respect to the θj ’s, and setting them to zero. This allows us to find the optimum theta without iteration. The normal equation formula is given below:
[![Screen-Shot-2018-12-14-at-4-28-36-AM.png](https://i.postimg.cc/9MBR8kvy/Screen-Shot-2018-12-14-at-4-28-36-AM.png)](https://postimg.cc/sQvg1Tf2)

[![Screen-Shot-2018-12-14-at-4-30-57-AM.png](https://i.postimg.cc/6qvs5stv/Screen-Shot-2018-12-14-at-4-30-57-AM.png)](https://postimg.cc/4Hs2BSKf)

## Normal Equation Noninvertibility


[![Screen-Shot-2018-12-14-at-4-34-52-AM.png](https://i.postimg.cc/qBXSwGg0/Screen-Shot-2018-12-14-at-4-34-52-AM.png)](https://postimg.cc/3WNtJmgb)



