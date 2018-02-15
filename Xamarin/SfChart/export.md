---
layout: post
title:  Exporting options in Essential Xamarin.Forms Chart 
description: How to export the Chart as an image
platform: xamarin
control: Chart
documentation: ug
---

# Exporting

**Export as an image**

The chart can be exported as an image in JPEG format using the [`SaveAsImage`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~SaveAsImage.html#) method of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html#).

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

sfChart.SaveAsImage("ChartSample.jpg");

{% endhighlight %}

The exported image will be saved in the following locations depends on the platforms:

* **Android**—The image will be saved in the "Pictures" directory.
* **iOS**—The image will be saved in the “Photos/Album” directory.
* **Windows**—The image will be saved in the “Pictures/Saved Pictures” directory.

N> To save the image in Android and Windows platforms, enable the permission to write the file in device storage.