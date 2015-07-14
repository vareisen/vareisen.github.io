---
layout: post
title: Android - Dialog
description: "Android - Dialog"
modified: 2015-07-14
tags: [android]
---

<b>1. Alert Dialog:</b><br>


{% highlight cpp %}
public void showAlertDialog(){
        AlertDialog.Builder dialog = new AlertDialog.Builder(this); // initialize an alert dialog
        dialog.setTitle("here is title"); // set the title for alert dialog
        dialog.setMessage("here is message"); // set messages...
        dialog.setPositiveButton("OK", new DialogInterface.OnClickListener() { // set OK button for alert dialog
            @Override
            public void onClick(DialogInterface dialog, int which) {
                Toast.makeText(getBaseContext(), "OK clicked!", Toast.LENGTH_SHORT).show();
                // or do something here !!!
            }
        });
        dialog.setNegativeButton("Cancel", new DialogInterface.OnClickListener() { // set cancel button
            @Override
            public void onClick(DialogInterface dialog, int which) {
                Toast.makeText(getBaseContext(), "Cancelled", Toast.LENGTH_SHORT).show();
            }
        });
        dialog.create().show(); // remember!!!
    }
{% endhighlight %}
