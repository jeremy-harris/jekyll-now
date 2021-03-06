---
layout: post
title: Product Recommendation Project – MBA & Apriori
published: true
---
## Question Posed:  
Can you help determine which products a client is most likely to purchase next based on historical data and customer demographics? 

## A Few More Details: 
A company has data showing customer information and what products the customers have purchased over time. These are tech products from an online technology retail store. The data is broken down by transaction and has information for each product that was purchased during the transaction. 

## Solution: Market Basket Analysis
A Market Basket Analysis or ‘MBA’ (no, not the MBA your brother-in-law brags about getting at every family gathering) is used to identify ‘interesting’ relationships or associations between products. At a high level, the MBA method will take a list of transactions (once cleaned up, of course) and uses the apriori algorithm to inspect the dataset and find all instances (called rules in this case) that match two main criteria: 
1.	How often items appear in the data (Support)
    a.	For example, how many times does a product (or set of products) occur in the data.
2.	How often items appear in the data and also appear with another item (Confidence)
    a.	For example, for every time diapers and beer appear together in the dataset (Support), how many times does beer also appear in the same transaction? 50% of the time, 70% of the time? This is the confidence interval of the algorithm. 

## But, don’t be fooled – this isn’t just for retail. 
Here’s a few examples of an MBA being used for some pretty cool predictive stuff: 
* Voting Prediction of Politicians
* [Target Knows You're Pregnant!](https://www.nytimes.com/2012/02/19/magazine/shopping-habits.html?pagewanted=all&_moc.semityn.www)
* What song you want to listen to next.
* What to offer clients that are about to leave you.

## Okay, So What Did I Do? 

### Took a Look at the Data: 
I used the apriori algorithm and tweaked the support and confidence until I was able to generate a sufficient number of occurrences (support) that had a pretty high likelihood of resulting in another purchase (confidence). 

*   I used a support of .005 (occurs .05% of the time) & confidence of 0.6 (60% or greater predicted result)
*   This generated a set of 28 rules (or qualifiying instanses based on my support and confidence numbers):
![Apriori Results](/images/apriori-results1.JPG)

### Inspected the Results Further
Next, I inspected the results to see which rules were the most valuable. I was looking at: 
*   What products were purchased the most? 
*   What products were purchased the least? 
*   How many times did an occurrence equate to the purchase of my most popular product? 

In general, I just wanted to get a feel for what was selling, what wasn’t and make sure that there weren’t any anomalies. In this case, there were. My biggest question to the sales team is that there were several times that multiple computers were purchased and they were all different make/model and brands. That’s pretty rare – and needs a little further explanation. 

![Apriori-Rules](/images/apriori-rules1.JPG)

*   So looking at the above output, you can see that 0.00528% of the time, the items were purchased together. In this case, Acer Aspire, Dell Desktop and a ViewSonic Monitor.
*   When that happens, it is 81.5% likely that the customer will also purchase an HP Laptop. 
*   And you can see that this actually happened 52 times.

## Summary
A Market Basket Analysis is a great way to be more efficient with your marketing by focusing on cases that you know are more likely to happen. This is true if you’re a retail store selling products, a bank marketing various services and loans to clients, online retailers, looking to reduce client churn or employee churn....and the list goes on.

## More Nerdy Details
We take the data and set our threshold for how often we want the condition to exist and how high we want the percentage that a subsequent result will occur. Obviously, we typically want to see something appear very often and also have a very high percentage of confidence that a subsequent result will occur. 

An example would be trying to predict a future product for a client. However, if items ‘a’ and ‘b’ were only purchased together 5 times that year out of say, 100,000 transactions, it may not be worth researching the confidence interval because it is such a rare occurrence. Unless, however, the confidence interval is very high and it is a high ticket/high profit item. Want more information on the details, you nerd? [This article](https://towardsdatascience.com/association-rules-2-aa9a77241654) should satisfy your knowledge desires. 

### Apriori Code Description
This is the code I used to generate the rules. At first, I went after a higher frequency and higher confidence, but there were not any rules generated. So, I had to start backing off of the frequency and confidence. I found a sweet spot which is the code below that generated 28 rules. Out of roughly 10,000 transactions, these purchases only happened 50-60 times which isn't terribly high; however, our confidence (likelihood of a result hapenning) is 74% or greater which means we should be able to predict the product they will buy next with > 74% accuracy. 

![Apriori Code](/images/apriori-code1.JPG)
