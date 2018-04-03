---
layout: post
title:  Exporting options in Essential Xamarin.Forms Chart 
description: How to export the Chart as an image
platform: xamarin
control: Chart
documentation: ug
---

# Exporting

## Export as an image

You can export the Chart as a JPG image using [`SaveAsImage`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~SaveAsImage.html#) method of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html#).

{% tabs %} 

{% highlight c# %}

SfChart chart = new SfChart();
...

chart.SaveAsImage("ChartSample.jpg");

{% endhighlight %}

{% endtabs %}

The exported image will be saved in the different location across the platforms.

**Android** – The image will be saved inside the Pictures directory.

**iOS** – The image will be saved inside the “Photos/Album” directory.

**Windows Phone** – The image will be saved inside the “/Pictures/ Saved Pictures” directory.

N> In order to save the image in Android and Windows Phone, you have to enable the permission to write the file in device storage.

## Get the stream of Chart

The GetStream method of SfChart is used to get the chart as stream. The output stream can be passed as an input of any other components which accept the stream such as pdf, excel, word etc.

{% tabs %} 

{% highlight c# %}

SfChart chart = new SfChart();
...

chart.GetStream();

{% endhighlight %}

{% endtabs %}
