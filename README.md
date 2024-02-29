# Loan-Default-Prediction-Decision-Trees

## ![#f03c15](https://placehold.co/15x15/f03c15/f03c15.png) Problem Statement 

A bank's consumer credit department aims to simplify the decision-making process for home equity
lines of credit to be accepted. To do this, they will adopt the Equal Credit Opportunity Act's
guidelines to establish an empirically derived and statistically sound model for credit scoring. The
model will be based on the data obtained via the existing loan underwriting process from recent
applicants who have been given credit. The model will be built from predictive modeling techniques,
but the model created must be interpretable enough to provide a justification for any adverse
behavior (rejections).

## ![#c5f015](https://placehold.co/15x15/c5f015/c5f015.png) Objective

Build a classification model to predict clients who are likely to default on their loan and give
recommendations to the bank on the important features to consider while approving a loan.

## ![#1589F0](https://placehold.co/15x15/1589F0/1589F0.png) Refined insights

1. **We built a classifier model that can predict if a customer applying for a loan will default or not with** an f-1 score of 70%, **a recall of 75%** and an overall accuracy of 87%.

> **This is a great achievement as it means the bank will be able to detect if a customer will default successfully 7.5 times out of 10**. In addition, our overall f-1 score on the target class which is here the defaulting one yields 70%. The overall accuracy is also excellent a few points below 90%.   

2. Not surprisingly, **we found that the debt-to-income ratio is a critical feature of importance in all our models**. The model we retained the tuned single decision tree gives it an extremely high importance at 80%, when its impact is still the most important in our non-retained boosted model but more balanced at around 1/3 importance.

> **21% of the values for that variable were missing, which is too high. We will raise that concern to the bank and ensure we have a process in place to get as close to 100% collection for that feature**, as it's so important to the validity of our predictions. Knowing that 80% of our model depends on that variable, we can't afford to have missing values here. We should also have data quality processes in place to ensure we don't have incorrect values either.

3. **In terms of missing values, we also will group with DEBTINC, DELINQ as being a very important variable for our model**, and therefore the importance to get all values for this variable too. Currently we have around 10% of values missing for this variable when it is our second most important variable impacting our prediction.

> **Having delinquent credit lines was consistently a factor increasing the likelihood of defaulting**. Even though most borrowers didn't have any of those flagged. Having them meant riskier profiles for the bank. **On a side note, the DEROG variable also appeared to be impacting our model in the boosted tree, but not in the single decision tree**. It might be worth monitoring this variable in the future, see if it ends up also being a feature of importance in our single decision tree.

4. **Other credit score related features such as the number of recent credit inquiries or the number of credit lines did provide some insights and impact on the likelihood of defaulting, at a lower level than the previously mentioned variables though**.

> A confirmation here that features contributing to the credit score calculation all proved helpful in our model to assess the likelihood of defaulting. We will confirm this information to the bank.

5. **On data quality, we found out that DEBTINC and CLAGE had outliers that didn't seem valid**. We clipped reasonable values for these variables when the debt-to-income ratio was above 100, and the years of credit history above 70 years.

> **I would spend time discussing with the bank about this. For the debt-to-income ratio even if values between 50 and 100 are technically possible, I seriously doubt any bank would provide loans to such risky profiles**. So maybe that means our values are incorrect, which in turn impacts the quality of our model. The bank will probably be able to respond to that and clear our doubts or fix it.

6. **The variable that give us the job position and job longetivity didn't prove that impactful on our model**, which we were not necessarily anticipating. These variables can be good proxies for job stabilty, financial strength and security.

> **I would talk to the bank about the JOB variable that has 45% of values that are equivalent to missing, as they refer to 'Other' jobs**. In addition categories of values are not mutually exclusive making it confusing. For instance we have an Office category and a Executive position, one refers to the type of job, the other one to the seniority. Maybe a better collected variable could help us improve our model.

7. **The loan value didn't seem at first to have a significant impact on the chances of defaulting (i.e., in the EDA when analyzed on the overall population of borrowers), but it consistently came back as one of the features of importance to our model at a lesser degree though compared to other stronger features of importance**. Once we get deeper into the tree, this variable seems to have more impact for subgroups of our population.

8. In terms of the type of loan we are providing, which are only home improvement and debt consolidation loans, the bank mostly provides the latter one at 70% of loans provided. **We didn't see a meaningful impact of the type of loan on the outcome of defaulting**.

> I would still keep a closer eye to home improvement loans as our boosted model, the XG Boost, seemed to attribute a slight importance of this value on chances of defaulting. **Overall, it would make sense to ask the bank if they plan to provide more type of loans in the future, there are many opportunities out there.** If we already have data on customers, it could also make sense to get into providing mortgages that are more lucrative.

9. **A less important element but still worth mentioning, is that the home property value variable and the outstanding mortgage due are very correlated, and so together don't add more value to our problem**

> **If the bank has the ability to switch one of these variables for other ones, such as more socio-economic criteria on the borrower (e.g., salary, age, address), we would want to do it.** It seems the dataset comes from the Home Equity dataset (HMEQ), that might be a discussion to have with them.
