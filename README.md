
INTRODUCTION

A/B testing (also known as split testing) is the process of comparing two versions of a web page, email, or other marketing asset by measuring the difference in performance.  For this project, I analysed an A/B test results for an e-commerce website to understand the results. 

The dataset is divided into two: __control and treatment group,__ the target is to measure the conversion rate for the two groups to determine if a new web page should be rolled out or not. 

This conversion rate for each group will tell whether the old page should be continued or discontinued and the the new page rolled out.

The goal of this project is to work through this data to help the company understand if they should implement the new page, keep the old page, or perhaps run the experiment longer to make their decision.

Three approaches was used for the analysis: 

PART I - Probability approach
After cleaning the data, I calculated mean to determine the proportion of each group that converted.  The result shows that the probability that an individual in the new page converted is `11%` which is almost the same as the probaility that old page converted at `12%`. My conclusion is that there is no sufficient evidence to say that the new treatment page leads to more conversion. If anything the old page has a `1%` higher rate of conversion.

PART II - A/B TEST
With a Type I error rate, P-value of 0.9 was computed, hence the we fail to reject the null hypotheses.

I calculated the proportion of the new page that converted compared to the old page that converted. Then I simulated random new set of transactions under null condition for the old and new page. 

I created a new sample of 10000 points from the random set of transactions, and stored in a list call p_diffs. p-value calculated as the difference between the means of p_diffs and the diff betwwn the number that converted from the actual original dataset was 0.9. 

For 5% type I error p-value needs to be < 0.05, to select the alternative  𝐻1 . But in this case it is 0.9, hence we fail to reject the null and choose the null hypothses.

PART III - Regression Approach

Logistic regression was applied to the same dataset. Dummy variables were created for the groups, statsmodels was used to instantiate regression model on the two columns. The summary result showed a p-value of 0.190. This value is different because for logistic regression the log is displayed instead of the actual result. 
 There is a difference when comapred to the results obtained from the A/B test. 

 Additional variable, "Country" was added to the dataset to analyse if it might affect the conversion rate for the two groups. There was still not enough evidence to prove it has an effect on the conversion rate. 

CONCLUSION

From the three approaches applied - (Probability, A/B Test and Regression approach) none gave enough evidence to conclude that the new page has higher conversion rate than the old page.

My conclusion will be to either go ahead and implement the new page or allow more time for more tests to have concrete evidence that the new page has higher conversion rate than the old page.
