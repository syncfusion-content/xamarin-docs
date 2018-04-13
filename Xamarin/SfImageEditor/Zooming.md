---
layout : post
title : Zooming and Panning operations in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to Zoom and pan the image in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Zooming

The image editor control provides support for zooming and panning. You can Zoom in and Zoom out the image in image editor control.

The following properties are used for zooming feature of the image editor control:

* EnableZooming
* Maximum ZoomLevel

### EnableZooming

You can enable or disable zooming by setting Enable Zooming to either true or false. By default, Enable Zooming is set to true.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor  EnableZooming="false"/>
     
{% endhighlight %}

{% highlight C# %}
   
     editor.EnableZooming = false;

{% endhighlight %}

{% endtabs %}

### Maximum ZoomLevel

You can customize the zoom level to maximum by setting the value to Maximum ZoomLevel property in image editor control.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor EnableZooming="true"  MaximumZoomLevel="8"/>
     
{% endhighlight %}

{% highlight C# %}

     editor.EnableZooming = true;
     editor.MaximumZoomLevel = 8;

{% endhighlight %}

{% endtabs %}

## Panning

Image editor control provides support for panning. Image editor allows you to pan the image with only two fingers to identify the touch interaction between panning and Resizing, or shifting shapes.


![SfImageEditor](ImageEditor_images/zoom.gif)


