---
layout: post
title: Android Diary - Custom ListView
description: "Android Diary - Custom ListView"
modified: 2015-07-20
tags: [Java, Android, ListView]
---

<img src="http://i.imgur.com/JwNSh9l.gif"> <br>
Custom listView.
<br>

<h1>Step 1:</h1> <br>
First, preparing data for the listview (strings, images...). <br>
 - With images, you should create new folder name "drawable" in <b>res</b> folder and paste all images to it (example 12 imgs below) <br>
<img src="http://i.imgur.com/bbvQ6ib.gif"> <br>

 - With strings, you should store it in <b>res/values/strings.xml</b>, create 2 string arrays as below: <br>
<img src="http://i.imgur.com/it3Nd86.gif"> <br>
remember the name for each string array (name, description), it's as same as the <b>id</b> for us to use in java code.
that's all we need in step 1.

<h1>Step 2:</h1> <br>
Create new layout that you want it display in single row. In my example, a single row has one imageview and two textview,
so we'll create a new layout as below: <br>
<img src="http://i.imgur.com/eU6Koay.gif"> <br>
and now go to the mainActivity.java, get all the widget from xml file we just created, see the picture below: <br>
<img src="http://i.imgur.com/bxIlZiG.gif"> <br>
return the main layout xml file, we add a listView to this layout, remember set ID for this listview. <br>

<h1>Step 3:</h1> <br>
Create 2 new classes name "CustomAdapter" or anything you want, this class is extends from <b>ArrayAdapter<></b> and <br>ViewHolder</b> class <br>
<img src="http://i.imgur.com/9kIpSnp.gif"> <br>
<img src="http://i.imgur.com/LFjJcVl.gif"> <br>
you see above, we have a constructor and a override method named <b>"getView"</b>, this method help we connecting 3 widgets in xml into 1 object and after that, returning it to the main activity class. <br>
The <b>ViewHolder</b> class help getting widgets in xml one times in the first times we load (when scrolling down), if review it in the seecond times, just get it from row (vh = (ViewHolder) row.getTag();) <br>
then we setText, setImageResource for widgets, finally we return the <b>row</b> <br>

<h1>Finally:</h1> <br>
Come back to the main Activity, see <b>onCreate</b> method below: <br>
<img src="http://i.imgur.com/Sd2ou8s.gif"> <br>
we call <b>CustomAdapter</b> and set this adapter for the listView, view params in line 38th carefully. <br>
To add event for listView, we add <b>setOnItemClick....</b>. I'll talk about this in later.
<br>
and result: <br>
<img src="http://i.imgur.com/JwNSh9l.gif"> <br>



<div class="fb-comments" data-href="https://www.facebook.com/photo.php?fbid=442718139235144" data-width="650" data-numposts="3" data-colorscheme="light"></div>
