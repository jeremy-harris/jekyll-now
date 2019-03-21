---
layout: post
title: Installing And Using Jupyter Notebook With R For The First Time!
published: false
---
### What is Jupyter? 
In short, Jupyter Notebook is an application that allows you to write code in several different languages, include description of your code and share it easily with other people. In essense, you can use it for collaboration as well as for showing off your work and allowing others to see "what you did" as well as execute live code. 

#### Step One: Installation
I run on Windows, but you can use Jupyter on a Mac, Linux or Windows. The recommendation from Jupyter is to install the Anaconda package that also includes Python which is needed for Jupyter Notebook to work (Jupyter Notebook was originally called iPython and was built for Python, but not includes a variety of languages). The installer and instructions are on the <a href="https://www.anaconda.com/distribution/" target="_blank">Anaconda installation page</a>. 

#### Step Two: Installing R kernal on Jupyter Notebook
I am working in R for now and will pick up Python later. By default, the kernal installed in Jupyter Notebook is Python. To add R, this video is the best I've seen showing the quick installation:
[![Add R To Jupyter](http://i3.ytimg.com/vi/SXBxKe8sK6I/hqdefault.jpg)](https://www.youtube.com/watch?v=SXBxKe8sK6I)

<b> Important Note:</b> <u>You need to use the Anaconda Prompt</u> (found by searching Windows/Start to run the code in the video. If you use the standard Windows prompt, the needed path is not added by default and the command 'conda' will not be found. 

#### Step Three: Open up Jupyter Notebook with R kernal
Launch the Jupyter notebook by executing the Jupyter Notebook application that you previously installed. You'll want to select 'New' and then R to launch an R Notebook. 

![Launch R Notebook](/images/Jupyter-R.JPG)
