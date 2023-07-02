# The essence of the work
The main goal of my work is to show how we can increase the test power based on additional information about our data. Additional information in my case is mean and weight of each group. This way of increasing the power of the test using splitting to control and experimental groups given weights and mean of each group is named stratification.
Also, I will show the bootstrap method that allows estimate a statistic we need (difference of means) and build for its confidence interval.

# About data:
I will generate data about purchases and also data labels with a category of clients - potential or regular. Data will be distributed exponentially because exponential distribution is one of the easy ways to approximate the behavior of people who makes purchases. Each category has its own values both of mean and weight (i.e. portion from the entire population).


# Design:
Before conducting A/B testing is essential to define the following key points:
 - choosing target metric. In my case, it will be a difference of means
 - formulate a null and alternative hypothesis. Null is there is no significant difference between groups or in other words a difference of means is equal to 0. 
 An alternative is there is a significant difference between groups or in other words a difference of means is not equal to 0.
 - alpha or I type error. Alpha is the probability of rejecting a true null hypothesis. I will set alpha to be equal to 0.05
 - beta or II type error. Beta is the probability of rejecting a true alternative hypothesis. Usually, II type error have more serious consequences for a business. 
 I will set the beta to be equal to 0.3. Knowing beta we can find out corresponding the power of the test from the following equality: power = 1 - beta = 1 - 0.3 = 0.7
 - MDE (minimum detectable effect) is the smallest effect that would matter in practice for the business and is usually set by stakeholders. I will set MDE to be equal to 100.
 - sample size. A minimum sample size of the control and experimental groups is based on parameters you define: power, alpha, MDE and variances of the two normally distributed samples of equal size. Apart from the calculation of sample size depends on an underlying metric that we will be tracking. In my case is a difference of means. Then we can use the Central Limit Theorem and state that the mean sampling distribution of both Control and Experimental Groups follow Normal Distribution. Consequently, the sampling distributions of the difference of means of these two groups also follow Normal Distribution.
 - сhoosing an appropriate statistical test. I will be using 2 sample t-test and the bootstrap method. An important point regarding the 2 sample t-test is following assumptions must be met: users in control and experimental groups are independent, p-values should be uniformly distributed under the true null hypothesis(AA test), target metric should be normally distributed according to Central Limit Theorem(i will define this with bootstrap).


## Let's dive into my work in more detail )
