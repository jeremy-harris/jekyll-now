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
a.	For example, how many times does a product (or set of products) occur in the data
2.	How often items appear in the data and also appear with another item (Confidence)
a.	For example, for every time diapers and beer appear together in the dataset (Support), how many times does beer also appear in the same transaction? 50% of the time, 70% of the time? This is the confidence interval of the algorithm. 
We take the data and set our threshold for how often we want the condition to exist and how high we want the percentage that a subsequent result will occur. Obviously, we typically want to see something appear very often and also have a very high percentage of confidence that a subsequent result will occur. An example would be trying to predict a future product for a client. However, if items ‘a’ and ‘b’ were only purchased together 5 times that year out of say, 100,000 transactions, it may not be worth researching the confidence interval because it is such a rare occurrence. Unless, however, the confidence interval is very high and it is a high ticket/high profit item. Want more information on the details, you nerd? <a href=”https://towardsdatascience.com/association-rules-2-aa9a77241654” target = “_blank”>This article</a> should satisfy your knowledge desires. 

### But, don’t be fooled – this isn’t just for retail. 
Here’s a few examples of an MBA being used for some pretty cool predictive stuff: 
•	Voting Prediction of Politicians
•	<a href=”https://www.nytimes.com/2012/02/19/magazine/shopping-habits.html?pagewanted=all&_moc.semityn.www” target=”_blank”>Target Knows You’re Pregnant, and how far along!</a>
•	What song you want to listen to next.
•	What to offer clients that are about to leave you.

## Okay, So What Did I Do? 

### Take a Look at the Data: 
I used the apriori algorithm and tweaked the support and confidence until I was able to generate a sufficient number of occurrences (support) that had a pretty high likelihood of resulting in another purchase (confidence). 

### Inspect the Results Further
Next, I inspected the results to see which rules were the most valuable. Things I was looking at were: 
•	What products were purchased the most? 
•	What products were purchased the least? 
•	How many times did an occurrence equate to the purchase of my most popular product? 
In general, I just wanted to get a feel for what was selling, what wasn’t and make sure that there weren’t any anomalies. In this case, there were. My biggest question to the sales team is that there were several times that multiple computers were purchased and they were all different make/model and brands. That’s pretty rare – and needs a little further explanation. 

![Sold](/images/C2T4 – Top 10 Sold.png)

## Final Findings: 
For this example, the final findings were that iMac and HP computers were top sellers and that if a client had either product in their cart, we need to show them both items because these two were purchased together so many times that it was more than a fluke. The advice was to market to anyone that had purchased a PC or Laptop recently 
## Summary
A Market Basket Analysis is a great way to be more efficient with your marketing by focusing on cases that you know are more likely to happen. This is true if you’re a retail store selling products, a bank marketing various services and loans to clients, online retailers, looking to reduce client churn or employee churn….and the list goes on. 
