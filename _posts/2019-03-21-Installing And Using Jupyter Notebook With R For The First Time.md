---
layout: post
title: Installing And Using Jupyter Notebook With R For The First Time!
published: false
---
### What is Jupyter? 
In short, Jupyter Notebook is an application that allows you to write code in several different languages, include description of your code and share it easily with other people. In essense, you can use it for collaboration as well as for showing off your work and allowing others to see "what you did" as well as execute live code. Think of it like a facebook - before, you just took pictures and kept them to yourself - now you take them and post in public to rub it in the face of those less fortunate...why do you do this to me, <a href="https://twitter.com/DanBilzerian" target="_blank">Dan Bilzerian</a>, why?!?

#### Step One: Installation
I run on Windows (I know, I'm sorry...), but you can use Jupyter on a Mac or Linux as well. The recommendation from Jupyter is to install the Anaconda package that also includes Python which is needed for Jupyter Notebook to work (Jupyter Notebook was originally called iPython and was built for Python, but not includes a variety of languages). The installer and instructions are on the <a href="https://www.anaconda.com/distribution/" target="_blank">Anaconda installation page</a>. It's point and click from there, similar to paint by numbers. Man, I miss those!

![Paint By Numbers](/images/paint-by-number.jpg)

I wonder what it will be once we color it in????

#### Step Two: Installing R kernal on Jupyter Notebook
I am working in R for now and will pick up Python later. By default, the kernal installed in Jupyter Notebook is Python. To add R, this video is the best I've seen showing the quick installation:
[![Add R To Jupyter](http://i3.ytimg.com/vi/SXBxKe8sK6I/hqdefault.jpg)](https://www.youtube.com/watch?v=SXBxKe8sK6I)

<b> Important Note:</b> <u>You need to use the Anaconda Prompt</u> (found by searching Windows/Start to run the code in the video. If you use the standard Windows prompt, the needed path is not added by default and the command 'conda' will not be found. 

#### Step Three: Open up Jupyter Notebook with R kernal
Launch the Jupyter notebook by executing the Jupyter Notebook application that you previously installed. You'll want to select 'New' and then R to launch an R Notebook. 

![Launch R Notebook](/images/Jupyter-R.JPG)

From here, you can start creating your own code right in the web browser! I found this video to be helpful as a basic explanation of how Jupyter works.  

[![Jupyter Intro](http://i3.ytimg.com/vi/jZ952vChhuI/hqdefault.jpg)](https://www.youtube.com/watch?v=jZ952vChhuI)
He is using Python, not R - but the execution is the same.

#### Step Four: Publish and Share!
Once you've created your notebook on your local machine, it's time to share it. Github to the rescue!


I created a really basic Jupyter Notebook with R to show a live view of the code in my last blogpost <a href="https://jeremy-harris.github.io/A-Newbie-Tries-Machine-Learning-and-Regression/" target="_blank">Newbie Tries ML & Regression</a>. Now, instead of just a link to code - I can provide a Jupyter Notebook the the live code that can be executed, edited and explained all on the web browser. Pretty cool. 

#### Spoiler: It's a Turtle

![Turtle](/images/turtle.jpg)

I know, disappointing. I thought for sure it was the Space X Dragon. Maybe next time. 
