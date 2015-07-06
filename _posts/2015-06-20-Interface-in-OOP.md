---
layout: post
title: What is Interface in OOP?
description: "What is Interface in OOP?"
modified: 2015-06-20
tags: [java]
---

<img src="http://i.imgur.com/NQQTAig.png"><br>

Let’s imagine.. 
<br>
You are rich and you have 50 houses, each house has a key. If you want to get into any  one of 50 houses, you have to remember the key for each. Is it difficult for you to get into? <br>
An brilliant IDEA for you is now we create a new KEY that we can get into any house! A key can unlock any lock of any 50 house there :) have you imagined it? It’s called Interface in OOP! With an Interface, you can access to any other class.<br>

Now continue, keep on imagining!<br>
Each house is one class we created.<br>
Each key (Usual key) is one method from that class. Unlocking the lock is missions of all methods. (Unlocking method in every house is different).<br>
Now the key we use to unlock any house is called Interface! <br>
Example:  - We have  <b>”TheKey”</b> interface below:
<br>
{% highlight java %}
Public interface TheKEY{
	Public void key();
}
{% endhighlight %}


And we have <b>two</b> other class that <b>implemented “TheKey”</b> interface as below: <br>

{% highlight java %}
Public class TheFirstHouse implements TheKey{
	Public void key(){
	// your code here
	}
}
{% endhighlight %}
<br>
{% highlight java %}
Public class TheSecondHouse implements TheKey{
	Public void key(){
	// your code here
	}
}
{% endhighlight %}

Lets see it ! <br>
Suppose we would like to get into <b>“TheFirstHouse”</b>? Just do this: <br>

{% highlight java %}
Public static void main(String[] agrs){
	TheKey object = new TheFirstHouse();
	object.key();
}
{% endhighlight %}

And if we want to get into <b>“TheSecondHouse”</b> <br>

{% highlight java %}
Public static void main(String[] agrs){
	TheKey object = new TheSecondHouse();
	object.key();
}
{% endhighlight %}
<br>
.... update
<br>
Comment below for more! :)

<div class="fb-comments" data-href="https://www.facebook.com/photo.php?fbid=441070399399918" data-width="650" data-numposts="3" data-colorscheme="light"></div>
