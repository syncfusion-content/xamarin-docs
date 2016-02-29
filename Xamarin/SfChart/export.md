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

You can export the Chart as a jpg image using `SaveAsImage` method of `SfChart`.

{% highlight c# %}
[C#]

SfChart chart = new SfChart();
...

sfChart.SaveAsImage("ChartSample.jpg");

{% endhighlight %}

The exported image will be saved in the different location across the platforms.

**Android** – The image will be saved inside the Pictures directory.

**iOS** – The image will be saved inside the “Photos/Album” directory.

**Windows Phone** – The image will be saved inside the “/Pictures/ Saved Pictures” directory.

N> In order to save the image in Android and Windows Phone, you have to enable the permission to write the file in device storage.