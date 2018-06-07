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
* PanningMode

### EnableZooming

You can enable or disable zooming by setting EnableZooming to either true or false. By default, Enable Zooming is set to true.

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

## PanningMode

Image editor control provides support for panning. Image editor allows you to pan the image with two fingers or single finger by setting the PanningMode in image editor.

The following properties are used in the panning.

* Single Finger – You can zoom or pan the image but it restrict the select or move the shapes.

* Two Finger – You can zoom or pan the image and also select or move the shapes.

By default, PanningMode value as TwoFinger.

{% tabs %}

{% highlight XAML %}

<imageeditor:SfImageEditor  EnableZooming="true" PanningMode="TwoFinger"/>

{% endhighlight %}

{% highlight C# %}

editor.PanningMode = PanningMode.TwoFinger;

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/zoom.gif)


