---
layout: post
title:  "Discover Python Functions"
date:   2017-06-19 20:32:04 -0400
categories: Python3
---
This post is more of a reminder to myself.

When I first started learning Python, I struggled with what I could use when. A cool trick that I discovered was dir and help in the Python interpreter.

If I wanted to see all the things I could do with an object in Python, I learned you just have to do the following.

{% highlight python %}
foo = 'bar'
dir(foo)
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
{% endhighlight %}

Doing 'dir(foo)' gives a list of all of the Python functions that you can use (at least in the standard Python library). Most of them make sense, but to get a bit more of a description about what they do, you can type:

{% highlight python %}
help(foo.strip)

Help on built-in function strip:

strip(...) method of builtins.str instance
    S.strip([chars]) -> str

    Return a copy of the string S with leading and trailing
    whitespace removed.
    If chars is given and not None, remove characters in chars instead.
(END)
{% endhighlight %}

This trick really helped me get more comfortable at Python at my own pace, and I am embarassed to admit that I have forgotten and relearned it often. Now with this post I have a permanent reminder! Hope it helps others too.

Bob
