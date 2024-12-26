# OVERVIEW:
Little did I know that Statistics is the backbone in data 😅 In this end-of-course project, I tackled 2 different case studies using Python and basic Stats to solve:
- *Case Study 1:* **Automatidata,** a fictional data consulting firm
- *Case Study 2:* **TikTok,** a short-form video hosting firm

# Case Study 1: Automatidata 🚕
## Link here: [Case_study_1: Automatidata](https://github.com/amy941/Google_Advanced_Module-4_Statistics/blob/main/Case_Study_1_%20Automatidata.ipynb)

## What I Learned:
  
**1) Compute a descriptive stats:**
First, take a glimpse at the big data to understand how the dataset is structured before proceeding. The following functions are used:

**pandas:** .describe(), .head(), .shape | **numpy:** .mean()

 ```python
 taxi_data.describe(include='all')
 ```

![describe()](https://github.com/user-attachments/assets/9b3dcf70-2f0c-41a5-9a3a-80af6de01a19)

✍ *.describe()* generates the table with basic descriptive stats: mean, std deviation, min/max, interquartile, etc.
     
```python
taxi_data.groupby('payment_type')['fare_amount'].mean()
```
✍ Use *.groupby()* to compute the mean value of fare_amount(price) for each group of payment_type (credit card, cash,...) in the sample data.

![avg mean](https://github.com/user-attachments/assets/1c9d15bb-1da5-43a8-816d-22337b4468da)   

✍*1-Credit card, 2-Cash, 3-No charge, 4: Dispute, 5-Unknown*
   
We're interested in payment_type: 1-Credit card and 2-Cash. **The table shows credit card users tend to pay more than cash users**, $13.4 and $12.2, respectively.     
 
 
**2) Conduct Hypothesis test and A/B test:**

```python
credit_card = taxi_data[taxi_data['payment_type'] == 1]['fare_amount'] 
cash = taxi_data[taxi_data['payment_type'] == 2]['fare_amount']
```
✍ Firstly, assigned variables, one for Credit Card and one for Cash.

Then, created **BOOLEAN** ```taxi_data['payment_type'] == 1``` checks if the payment type for a taxi ride is a **credit card** since **1** is assigned for credit card payment. It returns **True** for rows where the payment is **1** (credit card), and **False** for all other rows.

Next, ```taxi_data[taxi_data['payment_type'] == 1```, this part filters the ENTIRE dataset ```taxi_data``` to include only rows where payment type is **1** (True). It selects all the rows where customers used credit card to pay.

Finally, after filtering data for ONLY credit card payment, ```['fare_amount']``` extracts the columns that contain the fair amount for the selected rows. It gives you just the fare amounts for rides where the payment was made using a credit card ONLY.

Similar approach for Cash payment.

```python
stats.ttest_ind(a=credit_card, b=cash, equal_var=False)
```
Hypothesis testing: 

**NULL hypothesis:** There is **no difference** in *the average fare amount* between customers who use credit cards and customers who use cash.

**ALTERNATIVE hypothesis:** There is **a difference** in *the average fare amount* between customers who use credit cards and customers who use cash.

✍ Proceed with a two-sample t-test to compute p-value given 5% as the significant level.

Set ```equal_var=False``` because we don't want the 2 samples have the same variance.

Result shows p-value is extremely small which is significantly less than signigicant level 5%. Thus, we can confidently draw a conclusion to reject the NULL hypothesis. 

**3) Provide insights to stakeholders:** 





# Case Study 2: TikTok 🎵




# Tools I used:
**Python, GitHub**

# Conclusions:

# Closing Thoughts:
Statistics is tough 🙃 It took me over a month to get the hang of the basics (very basic). Regardless, I think I'm in a better place than I was last month 🐌🐌🐌
