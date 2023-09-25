---
layout: post
title: Exporting in Xamarin Charts control | Syncfusion
description: Learn here all about Exporting support in Syncfusion Xamarin Charts (SfChart) control, its elements and more.

platform: xamarin
control: Chart
documentation: ug
---

# Exporting in Xamarin Charts (SfChart)

## Export as an image

You can export the Chart as a JPG image using [`SaveAsImage`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_SaveAsImage_System_String_) method of [`SfChart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html).

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

['SfChart'](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html) contains the following methods to get the chart stream.

## GetStream

The [`GetStream`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_GetStream) method of SfChart is used to get the chart as stream. The output stream can be passed as an input of any other components which accept the stream such as pdf, excel, word etc. This method is only applicable for Android and iOS platforms only.

{% tabs %} 

{% highlight c# %}

SfChart chart = new SfChart();
...

chart.GetStream();

{% endhighlight %}

{% endtabs %}

## GetStreamAsync

The [`GetStreamAsync`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfChart.XForms.SfChart.html#Syncfusion_SfChart_XForms_SfChart_GetStreamAsync) method of SfChart is used to get the chart as stream asynchronously. 

N> This method will work only when the SfChart view in UI.

The following code snippet demonstrates the usage of this method:

{% tabs %} 

{% highlight c# %}

SfChart chart = new SfChart();
...

var stream = await chart.GetStreamAsync();

{% endhighlight %}

{% endtabs %}

N> You can refer to our [Xamarin Charts](https://www.syncfusion.com/xamarin-ui-controls/xamarin-charts) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms Charts example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/Chart) to knows various chart types and how to easily configured with built-in support for creating stunning visual effects.  

## See also

[How to export the Chart to the PDF document in Xamarin.Forms](https://support.syncfusion.com/kb/article/8342/how-to-export-the-chart-to-the-pdf-document-in-xamarin-forms?isInternalRefresh=False)

[How to apply the PDF document size to Xamarin.Forms Chart](https://support.syncfusion.com/kb/article/7771/how-to-apply-the-pdf-document-size-to-xamarin-forms-chart?isInternalRefresh=False)

