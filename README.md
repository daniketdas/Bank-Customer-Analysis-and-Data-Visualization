# Bank-Customer-Analysis-and-Data-Visualization

## Objective:
To give an intuitive view of the dataset so as to help the marketing department of the bank to identify the potential customers who have a higher probability of purchasing the loan.
## Data Source:
The dataset used in this project was obtained from Kaggle. The dataset contains customer details of a USA bank, including demographic information and banking behavior.
## Importation of Required Libraries and Data:
So, first I imported all required libraries i.e. pandas, numpy for dataframe and basic mathmatical operations, plotly, seaborn and matplotlib for data visualizations.
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/78258e6e-28ba-4c6c-93f2-e7b3c9909939)
* My dataset had 5000 datapoints and 14 columns. From which I dropped 2 irrelevant columns.

![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/2524b0bc-3b74-473e-aba0-e8f2b4e39e99)
* Then I checked for null values and found no null values in the dataset.
#### checking some statistical summary and frequency distribution of few important predictors using boxplot and histogram.
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/12e94c3d-f6fd-4122-a335-0d66bc298d13)

Some basic observations from these boxplots:
* As we can see from the Age plot that min age is 23 and max age is 67. q3, Age is 55 and it's very unlikely for someone under 23 and above 55 to take personal loan. So, we can targer customers between age 23-55.
* Max family member has been recorded here is 4 and min is 1.
* Income mosly varies between 39k to 98k. Where min income 8k indicates someone's minimum starting salary and 185k is the upper fence. Some outliers can be seen here too, where income reaches upto 224k per month.
* Education between 1 to 3 indicating their education level as undergraduation, graduation and post-grad/above levels respectively.
* Experience mostly varies between 10 to 30 yrs. It's very unlikely for someone with over 30 years of experience taking personal loan because they might be at the verge of their retirement and negative experience could be due to human error. So we can target customers who is having work experience between 10 to 30 years.

![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/283dbe8c-2bd3-4e5c-990f-1da8d25b77ac)

Few notable observations from these histogram plots:
* Most number of customers are falling in the age group 30-55.
* In case of Experience, 20-30 years of experience is comparetively higher. But intrestingly some experience lie under 0 (could be due to human error.)
* Monthly income mostly varies between 10k-80k dollars.
* Most of the customers are under-graduate followed by post-graduate and graduate.
* Income and CCAvg data are not normally distributed, they are positively skewed.
#### Replacing all the negative experience with the mean of all experience
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/37569a73-9a8a-4350-ad79-c8cdbcca02fe)
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/ff2f2487-8a5b-4571-9b12-e6fd35a4a7cb)

![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/06e04a76-8304-4436-9688-9eef90cf5471)

This replaced all the negative experiences with the mean of all experiences listed in that column.
## Correlation between variables:
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/caaf1721-9c8b-4545-b0bf-3e2f7dae5581)

From this heatmap it was evident that Age and Experience were highly correlated, so I removed Experience column from my analysis in order to avoid multicollinearity and deleted Exeperience instead of Age because Agw plays a more vital role in targeting potential customers.

#### Pie chart of education qualifications and account-holder-category of all the customers
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/6bf1ebf2-f749-4bc8-a403-3112f8a5fb25)

![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/0bf46546-50a1-422e-803d-d7d20216b828)

#### Comparing Income, Education and Credit card spending between the customers who already have personal loan and who don't have.
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/660b05ee-d2f5-4088-8687-c6fddf668267)
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/f630cc91-2bbf-4dff-94d5-bbe82495fa36)
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/12dba65f-4a24-4a84-a6b4-4c5e1973a15e)
* It is clear from these plots that income plays a big role in taking personal loan, because median income of those who have personal loan is much more than that of those who donn't.
* From distribution plot also it is evident that most of the person with personal loan earn more than the person with no personal loan.
* And from this distribution of CCAvg and Personal Loan we see that most of the people who have CCAVg = 0 (indicating no credit card) or spend very less using credit card, don't have any personal loan too. So Having credit card or a good credit score playes a role in getting personal loan from bank.
#### Now comparing usage of online transactions, credit card and Account-holer-category between the customers who already have personal loan and who don't have.
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/952eb85d-e206-4f7d-a963-62981d7c4523)
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/964ee414-6618-4345-b2e0-492f937966be)
![image](https://github.com/daniketdas/Bank-Customer-Analysis-and-Data-Visualization/assets/162815966/7f8e3a36-c6b4-4c4a-91c4-26141f87b125)

* Most of the existing customers don't have any security account and having a security account does not also impact taking personal loan as very few of the securities account holders have personal loan. Holding no security account might as well indicate their risk-averse mentality or their age could be on the higher side.
* Most of the customers use online mode transaction and customers using online payment mode tend to take personal lone more.
* Out of 5000 customers over 3000 don't use credit card.
* Over 4000 customers don't have any CD or Security account and out of them 90% did not take any personal loan.

## Recommendations:
From this analysis conducted over 5000 customers,

* Bank can target customers between 23-55 age group as the possibility of accepting personal loan is higher from their side.
* As we saw income and education have a positive impact on accepting personal loan. So bank should target those who are comparatively higher educated and earn decently.
* We can also check customers' credit card spendings, as high credit card spending indicates higher earning.
* Then almost 60% of customers use online banking, bank can check their their spending pattern and design a personal loan for them.
* ~87% of the customers do not hold any of CD or Security accout, bank can target them for personal loan.



