---
layout: post
title: A Newbie Tries Machine Learning and Regression
published: true
---
Right off the bat the University of Texas program has us fire up RapidMiner and start working on a Machine Learning (ML) project. First a classification project and then a regression project. 

The regression project is asking this question, <b>"We have a list of 17 potential new products to release to market, but only want to pick the top 5. Can you take our past sales data and help us decide which 5 to pick?"</b>. 

Seems easy enough and did I ever learn about the effects of feature bias, forgetting to remove variables with a 1-to-1 correlation to the target value and finally, I know a little more about Poisson vs. Normal distribution. Let's dive in to my mistakes as I hacked through this project, painfully, like Tom Hanks in Castaway trying to yank out a tooth.

### Correlation Matrix Results
First, the correlation matrix. From here, I was looking for any variable that had a high correlation to another variable as well as any variable that has a high correlation to the target variable (volume). In this case, you can see that I have a few (in red) and a few that I think are irrelevant (in yellow) with a low correlation: 

![Matrix](/images/Correlation-Matrix-C1T2-1.jpg)

From here, I deleted the following values:
* X2-star-review because it has a high correlation with X1-star-review
* X4-star-review because it has a high correlation with X3-star-review
* X5-star-review because it has a perfect 1 correlation with my target variable (volume)
* product height, width, depth, weight because they have a low correlation with the target variable. 

I removed one of the variables with a high correlation to each other because I believe it is like 'double-dipping' and will have too much weight on the target variable. I remove the perfect correlation with the target value because it is an error and will virtually the only variable used for predictions, which isn't correct. Lastly, I removed the low correlation variables because they aren't relevant and will just increase the time it takes to run the models in the future. This is more relevant on much larger datasets. 

Here's a copy of my pared down correlation matrix: 

![Matrix](/images/Correlation-Matrix-C1T2-2.jpg)

I could probably remove a few more variables, especially profit margin as the correlation is near zero, but I left it for now. My rationale was that I didn't want to get down to just 2-3 variables. I'm not sure if that's a good reason or not, but that is why I left the variables. 

### Normalization and Filtering...Say What?
So now I get to go down the rabbit hole of normalization. I read a few <a href="https://www.statisticshowto.datasciencecentral.com/normalized/" target="_blank">articles</a> on it and understand that the idea is to get the data on the same scale. Think of trying to decide which team is better between the Yankees and the Patriots using only the final score of each game. It would be pretty hard to determine given the vast difference of the final scores. To do this, you would normalize the scores so that they are both on the same scale. I normalized all remaining values except for volume because it is my target value (the value I am trying to predict) so I don't want to alter its true value. 

Filtering is pretty simple. I need to remove outliers from the model. As you can see, I have 2 variables that are just out of whack. I'm not sure why (because I don't get to ask the test robot, but the variable that are so high aren't in my test data). These high values can throw off the model because the model may try to "fit" other values really high or off of the mark as well, so in this case they gotta go. 

Here you can see the two values that are a little different than the rest. 
![Outliers](/images/C1T2-outliers-1.jpg)

### Model Selection and Tuning (RMSE & r-squared)
From here, I trained three different model types on the data: 
* k-NN (Nearest Neighbor)
* SVM (Support Vector Machine)
* GBT (Gradient Boosted Trees) with <a href="https://www.theanalysisfactor.com/differences-between-normal-and-poisson-distributions/" target="_blank">Poisson distribution</a>. (I had to learn why this was relevant, thanks Ms. Karen Grace-Martin)

I'll spare you the hours of tuning to get the models to their optimal result. Here's the skinny: on each model, there are different variables that you can change to see how it effects the model performance based on your particular dataset. I'm looking at the output to observe the RMSE (Root Mean Squared Error) as well as the r-squared value. There are several writeups on both of these, <a href="https://www.theanalysisfactor.com/assessing-the-fit-of-regression-models/" target="_blank">this one</a> I found to be very useful. I'm looking for a low RMSE number and a high r-squared number. In my case, the best model for the data set I'm working with was GBT. However, <b> an important thing to remember is that an r-squared number of well over 0.925 is probably artificially high and indicates that you have a problem with your data selection or modeling</b>. I learned this the long and painful way - seems to be how I like to learn. Maybe I'm a data science learning masochist. Not sure if that's a thing. Anyhow....

### Here Are The Model Results....Good and Bad
#### Here is the result before I removed many values from the model: 
Notice the "ok" RMSE (not high or low, just ok). There's just too much noise in the variable set to really predict much better at this point. 
![GBT](/images/GBT-1.jpg)

#### Here is the result when I messed up and left in X5-star-reviews...
See how crazy good the model is? Perhaps too good? Well, that's because it is. When I forgot to remove the X5-star variable (remember, X5-star-review had a perfect 1 to 1 correclation with volume) the model thought that it could predict the model to near perfection because it so heavily weighted the outcome on one variable which just wasn't true in this case. If you get numbers "this good" - then you're wrong. You're not that good. Don't ever forget it. Ahhh, reminds me of my childhood. 
![GBT](/images/GBT-2.jpg)

#### And Here Is The Result All Tuned Up
Finally, after removing the variables, normalizing the data, filtering outliers and tuning the model properly....I get these parameters. 
![GBT](/images/GBT-3.jpg)

### All Trained Up and Ready to Test!
From here, I take my tuned up model and run a new set of data through it. Again, I'm trying to predict the sales volume of the products using regression testing with the GBT model that I tuned up. When I point the csv file at the model, the model adds in the 'predicted volume' column. 

Now I need to calculate the 'Total Profit' per item by multiplying the 'Price' x 'Profit Margin' x 'Predicted Sales Volume' (Price and Profit Margin are given in the csv file). Then, we will sort by the 'Total Profit' and get the top 5 items to present to sales.

### Yay! I Get to Use R To Clean Data!
I love working with R and any chance I get to read in spreadsheets and clean them up, I take it! I'm still new, so please don't yell at me <a href="https://twitter.com/hadleywickham" target="_blank">Hadley Wickham</a> for not having the correct file paths - I'll get there. 

Here's my code to read in the spreadsheets, clean them up (so I can use them in RapidMiner) -- then take the model output, merge two files into one and calculate 'Total Profit' and then sort and write the file to disk. Here's <a href="https://github.com/jeremy-harris/Prep-Clean-Store-C1T2/blob/master/clean_csv_files.R" target="_blank">My R Code</a>. -- <b> If you know how to get this code inline on my blog instead of just a link, please let me know. For some reason, it's not clicking in my brain.</b>

### And The Moment We've All Been Waiting For....A Pretty Chart
Okay, all of that to get us to this - the final output. Here you go sales team, release these products and go sell something. <a href="https://youtu.be/QMFwFgG9NE8" target="_blank">Coffee is for Closers</a>!

![Top Products](/images/Top-Products.jpg)

Until next time...stay clean, data...stay clean.
