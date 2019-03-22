---
layout: post
title: Installing And Using Jupyter Notebook With R For The First Time!
published: true
---
## What is Jupyter? 
In short, Jupyter Notebook is an application that allows you to write code in several different languages, include description of your code and share it easily with other people in a web browser. In essence, you can use it for collaboration as well as for showing off your work and allowing others to see "what you did" as well as execute live code. Think of it like a Facebook - before, you just took pictures and kept them to yourself - now you take them and post in public to rub it in the face of those less fortunate...why do you do this to me, <a href="https://twitter.com/DanBilzerian" target="_blank">Dan Bilzerian</a>, why?!?

## Step One: Installation
I run on Windows (I know, I'm sorry...), but you can use Jupyter on a Mac or Linux as well. The recommendation from Jupyter is to install the Anaconda package that also includes Python which is needed for Jupyter Notebook to work (Jupyter Notebook was originally called iPython and was built for Python, but not includes a variety of languages). The installer and instructions are on the <a href="https://www.anaconda.com/distribution/" target="_blank">Anaconda installation page</a>. It's point and click from there, similar to paint by numbers. 

![Paint By Numbers](/images/paint-by-number.jpg)

Man, I miss those! I wonder what it will be once we color it in????

## Step Two: Installing R kernel on Jupyter Notebook
I am working in R for now and will pick up Python later. By default, the kernel installed in Jupyter Notebook is Python. To add R, this video is the best I've seen showing the quick installation:
[![Add R To Jupyter](http://i3.ytimg.com/vi/SXBxKe8sK6I/hqdefault.jpg)](https://www.youtube.com/watch?v=SXBxKe8sK6I)

<b> Important Note:</b> <u>You need to use the Anaconda Prompt</u> (found by searching Windows/Start to run the code in the video. If you use the standard Windows prompt, the needed path is not added by default and the command 'conda' will not be found. 

## Step Three: Open up Jupyter Notebook with R kernel
Launch the Jupyter notebook by executing the Jupyter Notebook application that you previously installed. You'll want to select 'New' and then R to launch an R Notebook. 

![Launch R Notebook](/images/Jupyter-R.JPG)

From here, you can start creating your own code right in the web browser! I found this video to be helpful as a basic explanation of how Jupyter works.  

[![Jupyter Intro](http://i3.ytimg.com/vi/jZ952vChhuI/hqdefault.jpg)](https://www.youtube.com/watch?v=jZ952vChhuI)

He is using Python, not R - but the execution is the same.

### My First Jupyter Notebook
I launched Jupyter and created a new folder for my first notebook. I called mine C1T2 for 'Course 1, Task 2' of the class I'm taking. Inside of the folder, I uploaded the necessary csv and xlsx files that I need to perform actions on. There's a pretty simple video [here](https://www.youtube.com/watch?v=dJO3Zv9Va2E) that walks you through it.

I created a really basic [Jupyter Notebook with R](https://github.com/jeremy-harris/Prep-Clean-Store-C1T2/blob/master/C1T2_Clean_csv_and_xlsx.ipynb) to show a live view of the code in my last blogpost [Newbie Tries ML & Regression](https://jeremy-harris.github.io/A-Newbie-Tries-Machine-Learning-and-Regression/). Now, instead of just a link to code - I can provide a Jupyter Notebook the the live code that can be executed, edited and explained all on the web browser. Pretty cool. 


I inserted my R code that I previously created and changed the paths to the file names to match the new location in the C1T2 folder I created for Jupyter. I removed the final write portion of the code and instead changed it to a graph that I was able to put inline. Next, we share this with the world - I'm sure the world is waiting!

## Step Four: Publish and Share!
Once you've created your notebook on your local machine, it's time to share it. Github to the rescue! This is honestly pretty simple. Go to your Github repository of choice and upload the notebook - it will have an extension of .ipynb. If you need help, [this website breaks it down.](https://reproducible-science-curriculum.github.io/sharing-RR-Jupyter/01-sharing-github/)

## Spoiler: It's a Turtle

![Turtle](/images/paint-by-number2.jpg)

I know, disappointing. I thought for sure it was the Space X Dragon. Maybe next time. 


Until next time.....share that data!
