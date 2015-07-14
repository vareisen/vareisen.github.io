---
layout: post
title: Android Diary - Dialog
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


<b>2. Date Picker Dialog:</b><br>

{% highlight cpp %}
public void showDatePickerDialog(){
        DatePickerDialog.OnDateSetListener callback = new DatePickerDialog.OnDateSetListener() {
            @Override
            public void onDateSet(DatePicker view, int year, int monthOfYear, int dayOfMonth) {
                tvDate.setText((dayOfMonth) + "/" + (monthOfYear+1) + "/" + year); // update the textview "tvDate" with new values.
                cal.set(year, monthOfYear, dayOfMonth);
                dateFinish = cal.getTime();
            }
        };
        String s = tvDate.getText()+""; // get the current string values of "tvDate" textview
        String strArrtmp[] = s.split("/"); // split the string values by "/" into "strArrtmp" array.
        int dayTemp = Integer.parseInt(strArrtmp[0]); // convert the first value in strArrtmp array to an integer value
        int monthTemp = Integer.parseInt(strArrtmp[1])-1;
        int yearTemp = Integer.parseInt(strArrtmp[2]);
        DatePickerDialog pic = new DatePickerDialog(this, callback, yearTemp, monthTemp, dayTemp);
        pic.setTitle("Choose your date time:");
        pic.show(); // show the dialog
    }
{% endhighlight %}

update ......
