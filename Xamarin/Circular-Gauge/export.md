---
layout: post
title:  Exporting options in Syncfusion.Xamarin.Forms SfCircularGauge
description: This section describes how to export the SfCircularGauge as an image and get the stream of Syncfusion.Xamarin.Forms SfCircularGauge.

platform: xamarin
control: SfCircularGauge
documentation: ug
---

# Export SfCircularGauge as an image and get the stream

## Export as an image

You can export the circular gauge as an image using [`SaveAsImage`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.SfCircularGauge.html#Syncfusion_SfGauge_XForms_SfCircularGauge_SaveAsImage_System_String_) method of [`SfCircularGauge`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.SfCircularGauge.html).

{% tabs %}

{% highlight c# %}

SfCircularGauge circularGauge = new SfCircularGauge();
...

circularGauge.SaveAsImage("circularGauge.jpg");

{% endhighlight %}

{% endtabs %}

The exported image will be saved in the different location across the platforms.

**Android** – The image will be saved inside the Pictures directory.

**iOS** – The image will be saved inside the "Photos/Album" directory.

**UWP** – The image will be saved inside the "/Pictures/Saved Pictures" directory.

N> In order to save the image, you have to enable the permission to write the file in device storage.


## Get the stream of SfCircularGauge


The [`GetStream`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.SfCircularGauge.html#Syncfusion_SfGauge_XForms_SfCircularGauge_GetStream) method is used to get the circular gauge as stream asynchronously. The output stream can be passed as an input of any other components which accept the stream such as pdf, image etc.

{% tabs %}

{% highlight c# %}

SfCircularGauge circularGauge = new SfCircularGauge();
...

var stream = await circularGauge.GetStream();

{% endhighlight %}

{% endtabs %}