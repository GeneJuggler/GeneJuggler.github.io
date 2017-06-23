---
layout: post
title:  "Importing text with Tkinter"
date:   2017-06-22 21:38 -0400
categories: Python3 Tkinter
---
A common operation I've been doing in Python is importing text to use in whatever program I am designing. The simple way to import text is to manually type in the path, but I am a typo monster. TYPO MONSTER! As the late great Billy Mayes would say, "There has to be a better way!"

Tkinter, the default graphical user interface package for Python, has built in options to use the system dialogue to navigate to files. My first attempt was as follows:

{% highlight python %}
from tkinter import filedialog
filename = filedialog.askopenfilename()
{% endhighlight %}

Unfortunately a blank window opens up and the dialogue gets left in the background. To get the dialogue to appear in the front I had to add quite a bit more...

{% highlight python %}
from tkinter import Tk, filedialog
from os import system
from platform import system as platform

root = Tk()
root.withdraw()

def getTextFile():
    if platform() == 'Darwin':
        system('''/usr/bin/osascript -e 'tell app "Finder" to set frontmost of process "Python" to true' ''')
    else:
        root.lift()
    filename = filedialog.askopenfilename()
    if filename[-3:] != 'txt':
        print("Please select a txt file.")
        raise SystemExit()
    text = open(filename, 'r')
    return(text.read())
{% endhighlight %}

There is a lot more going on in this second version. Using root.withdraw() removes the Tkinter window. The whole series of commands with the OS is more of a Mac specific thing. In Linux and Windows, root.lift() will take the dialogue box to the top. For some reason the Mac terminal has priority and you have to dig around for the dialogue. The system(.... command is Mac specific and gets everything where it is supposed to be.

This may be a silly program, but it makes the finding of text files in my python projects way nicer. Hopefully this helps you too!

Bob
