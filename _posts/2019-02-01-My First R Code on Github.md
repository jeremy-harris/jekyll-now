---
layout: post
title: Putting R Code on Github
published: true
---
I've been taking online courses from <a href="http://www.datacamp.com" target="_blank">DataCamp.com</a> for a little over a month now. I decided to try and put some of the new skills to the test (another blog on that later). My venture into the unknown wild so far has just been to clean up spreadsheets for <a href="http://www.itmindshare.com" target="_blank">ITMindshare.com</a>. 

My latest project was to take all customer contact information for the past 12 months out of QuickBooks and generate a single list of unique email addresses. As you can guess, the report from QB had some missing data and duplicate data. I first went through manually and deleted people that I don't want to contact. Let's just say...it doesn't always end well. Then, I fired up RStudio (and Google) and got to work. I had a little help from my friend Jamie Field (professor at WVU) as well. 

You can see the code here: https://github.com/jeremy-harris/Clean_Customer_List/blob/master/Customer%20Contact%20Cleanup.R

This is about my learning experience with uploading the code to GitHub. I've never done this before so this is literally starting at zero (other than I did sign up for a GitHub account previously). First, I went to Google and found this <a href="https://happygitwithr.com/rstudio-git-github.html" target="_blank">article</a> which let me know I'd also need Git. I already have the other prerequisites. I used the document to get to the Windows installer and downloaded and installed Git. I clicked through, didn't change any options. I tried to start a new Git Project (per the documentation) and found that where I installed Git, wasn't in the system path. The fix for this is to close RStudio after Git is installed, then reopen RStudio. 

I was able to get through 12.3 in the document and clicked on my code (insted of the README.md file) in 12.4. I clicked on the Commit button and then did a push. However, the code didn't show up - just some sort of text file basically saying I did a commit. 
!(https://github.com/jeremy-harris/Clean_Customer_List/blob/master/Git_Pic.JPG)

After 10-15 minutes of still not figuring out why my files don't show up in the repository, I just clicked the nice little "upload file" button on GitHub and did the ol' drag and drop. Done.

I still need to figure out how to write code and save changes to GitHub. Mostly for version control and assuming one day I'll collaborate with others on projects, etc. For now, I just wanted to see my first code online. It's so pretty - just look at it! Okay, it's actually pretty boring and basic - but hey, I did it!

