# The essence of the work
The main goal of my work - show how can increase the test power with reducing a variance in two groups is based on additional information about our data. Additional information in my case is average and weight of each group. This way of increasing power of test using splitting to control and experimental groups given weight and average each groups is named stratification.
Also i will show bootstrap method that allow estimate a statistic we need (difference of means) and build for her confidence interval.

# About data:
i will generate data about purchases and also data label with category of client - potential or regular. Date will be distributed exponentially because exponential distribution is one of easy ways to approximate a behavior of people who make purchases. Each category have his own both values of average and weight (i.e. portion from entire population).


# Design:
Before conducting A B testing they are necessary to define following key points:
 - choosing target metric. In my case it will be difference of means
 - formulate null and alternative hypothesis. Null is no significant differences between groups or other words is difference of means is equal 0. 
 Alternative is there are significant differences between groups or other words is difference of means is not equal 0.
 - alpha or I type error. Alpha is probability of rejecting true null hypothesis. I will set alpha is equal 0.05
 - beta or II type error. Beta is probability of rejecting true alternative hypothesis. Usually II type error have more serious consequences for business. 
 I will set beta is equal 0.3 . Knowing beta we can find out corresponding the power of test from following equality: power = 1 - beta = 1 - 0.3 = 0.7
 - MDE (minimum detectable effect) is the smallest effect that would matter in practice for the business and is usually set by stakeholders. I will set MDE is equal 100.
 - sample size. Minimum sample size of the control and experimental groups is based on defined by yourself parameters:  power, alpha, MDE, and the variances of the two Normally Distributed samples of equal size. And also calculation a sample size depends on underlying metric that we will be track. In my case is difference of means. Then we can use the Central Limit Theorem and state that the mean sampling distribution of both Control and Experimental Groups follow Normal Distribution. Consequently, the sampling distributions of difference of means of these two groups also follow Normal Distribution.
 - сhoosing an appropriate statistical test. I will be use 2 sample t-test and bootstrap method. Important point regarding the 2 sample t-test is following assumptions must be met: users in control and experimental groups are independent, p-values should be uniformly distributed under true null hypothesis(AA test), target metric should be normal distribututed according to Central Limit Theorem(i will define this with bootstrap).


## Let's dive into my work in more detail )
