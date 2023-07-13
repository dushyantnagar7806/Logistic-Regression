
# Logistic Regression 

Before you start building logistic models, it will be helpful to understand the classification problems and the mathematical concepts that will help you solve these problems. So, this session will start there and then build on it. You will learn how to derive the cost function of this algorithm and how to minimise it.

## The Classification Function

Classification essentially involves splitting the given data set into different classes depending on 
its features. 
For instance, suppose a telecom company collects all types of data from a customer, such as their 
monthly data usage, minutes of calling and demographic information, and it can predict the 
customer’s monthly bill using this information. A monthly bill is a continuous variable and can 
have numerous different values. On the other hand, if the company tries to investigate whether 
a customer is likely to migrate from its network or not (this is called churn), then the output will 
have only two values, either true or false. This is the classification problem. 
One of the most fundamental algorithms to solve classification problems is logistic regression

classification essentially involves splitting the given data set into different classes depending on its features. For instance, suppose a telecom company collects all types of data from a customer, such as their monthly data usage, minutes of calling, and demographic information, and it can predict the customer’s monthly bill using this information. A monthly bill is a continuous variable and can have numerous different values. On the other hand, if the company tries to investigate whether a customer is likely to migrate from its network or not (this is called churn), then the output will have only two values, either true or false. This is the classification problem. 

 

Classification is a common problem that can be found in a lot of industries, such as predicting whether or not a person is likely to leave a company, contract a certain disease, buy a product, default on their loan payments, etc. One of the most fundamental algorithms to solve such classification problems is logistic regression.


1. The step function can have only two outputs: 0 or 1. Although this seems like an ideal property, it is not. The data used in the example was quite idealistic; however, in real data sets, some datapoints will be mixed as shown in the image given below, the labels for this data set are true and false. 
For data sets with mixed labels which are mostly the case with real data sets, the binary output functions are not suitable. As there is no clear threshold, which is the only dependent variable of the step function, it can be said that the step function is quite rigid and its application is limited to the cases where a threshold can be easily identified. Ideally, you would want your function to be applicable in all situations; this property of being applied universally is called generalisability.

To make the classification generalisable, you can make the function that is used to classify,  estimate the probabilities of a datapoint belonging to a particular class. Also, if you have probabilities, then you can then make an informed decision about the threshold

2. The step function is not differentiable. Most of the functions used in machine learning algorithms need to be differentiable. The reason behind this is that in some cases when the analytical solution fails, the solution is usually achieved using an iterative procedure that involves calculating gradients.
If you recall the module on linear regression, a cost function was built using the equation of a straight line and the cost function was minimised by equating the gradients to zero.
In logistic regression, similar steps will be performed to arrive at the best-fit model. So, the function used to separate the classes needs to be differentiable. 

**Step Function (Sigmoid)**
sigmoid is the function that shall satisfy the above criteria as it is used in Logistic Regression.

- the sigmoid function has all the properties that make it a suitable classification function. 

 

1. `It is bound between 0 and 1`.
Regardless of the value of x, the output of y will be between 1 and 0. This makes it ideal for predicting probabilities. 
 
2. `The function is asymptotic`, that is, it can never take the value of 0 or 1. 
The function can be 0 only if the numerator is 0, which will never happen, and it can be 1 only when e^(-x) = 0, which will also never happen. This adheres to the probabilistic approach, which states that no datapoint can be classified with 100% confidence. The chance of a datapoint belonging to a particular class is high


3. `The sigmoid function is a good classifier like the step function.` 
The sigmoid function resembles the step function, that is, the slope of the curve close to the ends is low. And the slope in the middle is high. So, the sigmoid function will have good separation for the datapoints that fall in the middle region. 
 
4. `It is easy to set a threshold for the sigmoid function`. 
At x = 0, the output of the sigmoid equals 0.5. If 0.5 is set as the threshold then if the value of x is positive, the datapoint is classified as 1, and if it is negative, the datapoint is classified as 0.


`Logistic Regression is used when the dependent variable(target) is categorical.`

## Types of Logistic Regression:

**1. Binary Logistic Regression**

The categorical response has only two 2 possible outcomes. Example: Spam or Not


**2. Multinomial Logistic Regression**

Three or more categories without ordering. Example: Predicting which food is preferred more (Veg, 
Non-Veg, Vegan)

**3. Ordinal Logistic Regression**
Three or more categories with ordering. Example: Movie rating from 1 to 5


## Mathematical Tools and Concepts needed to solve a Classification problem.

**1. Sigmoid function:**
Best suited to convert the continuous output of the term to 
probabilities. This is the probability of getting a positive class, given the features of the data. 

**2.Bernoulli distribution:**
 Gives the distribution of the dependent variable, the labels of the 
classification problem, the dependent variable has discrete binary outputs. Furthermore, the 
Bernoulli distribution was used to build the function which gives the probability mass function 
for a Bernoulli process. 


**3.Odds and log odds:** It helps in interpreting the change in the inputs to the change in the 
probability of the positive class.

**4.Gradient descent algorithm:** This algorithm helps minimise the log loss cost function; the 
negative sign of the gradient of the log loss function gives the direction in which the minima 
will be found, and its magnitude gives information about how big a step you can take in an 
iteration.


## Logistic model building:

**Likelihood function:** It gives the likelihood of the guessed labels being equal to the actual labels. This 
is calculated by combining the PMF of the Bernoulli process with the sigmoid of the 


**Maximum likelihood Estimation:** Taking the logarithm and simplifying the likelihood function will 
give the log-likelihood function. The log-likelihood function gives the probability the variable y, pi 
being equal to the actual variable yi given the parameters of the model: weights & bias/ intercept. To 
fit the assumed parameter to the given data, the log-likelihood needs to be maximised. This process 
is called Maximum likelihood estimation. 

**Minimising the log loss function:** In machine learning, it is preferred to minimise a function. So the 
sign of the maximum likelihood function is flipped to get the log loss function that can be minimised. 
The sigmoid of is substituted into the log loss function, and then it is minimised. 


**Gradient optimisation for the log loss function:** The gradient descent algorithm is used to find the 
weights which will give the minimum loss. Using the weights after convergence and the sigmoid 
function the predictions are made for the unseen data points 

**Evaluation metrics for the classification problems:**
As the classification problem fundamentally differs from the regression problem, the metrics used to 
evaluate the models are also quite different. 
1. Accuracy 
2. True accuracy 
3. Sensitivity and specificity 
4. Precision and recall
5. F1 Score 
6. ROC curve and area under it
