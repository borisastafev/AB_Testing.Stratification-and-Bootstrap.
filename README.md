# About data:
i will generate data about purchases and also data label with category of client - potential or regular. Date will be distributed exponentially because exponential distribution is one of easy ways to approximate a behavior of people who make purchases. And also each category have his own both values of average and weight (i.e. portion from entire population).

The main goal of my work - show how can increase the test power with reducing a variance in two groups is based on additional information about our data. Additional information in my case is average and weight of each group. This way of increasing power of test is named stratification.

Design:
Before conductiong AB testing they are nessesary to define following key points:
 - alpha or I type error. Alpha is probability of rejectiong H0 while Ho is true. I will set alpha is equal 0.05
 - beta or II type error. Beta is probability of rejectiong H1 while it is true. Usually II type error have more serious consequences for business. 
 I will set beta is equal 0.3 . Knowing beta we can find out the power of test from following equality: power = 1 - beta = 1 - 0.3 = 0.7
 - MDE (minimum detectable effect) is the smallest effect that would matter in practice for the business and is usually set by stakeholders. I will set MDE is equal 100.
 - sample size. Minimum sample size of the control and experimental groups is based on power, alpha, MDE, and the variances of the two Normally Distributed samples of equal size. And also calculation a sample size depends on underlying metric that we will be track. In my case is mean. Then we can use the Central Limit Theorem and state that the mean sampling distribution of both Control and Experimental Groups follow Normal Distribution. Consequently, the sampling distributions of difference of means of these two groups also follow Normal Distribution. The difference of means i will need in bootstrap method case
 - сhoosing an appropriate statistical test. I will be use 2 sample t-test and bootstrap method. Important point regarding the 2 sample t-test is all assumptions must be met: p-value distribution during conducting A/A test 
