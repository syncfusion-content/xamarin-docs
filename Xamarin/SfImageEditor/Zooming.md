---
layout : post
title : Zooming and Panning operations in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to Zoom and pan the image in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Zooming

The image editor control provides support for zooming and panning actions over an image.

The following properties are used for zooming feature of the image editor control:

* EnableZooming
* Maximum ZoomLevel
* PanningMode

## EnableZooming

You can enable or disable image zooming functionality by setting `EnableZooming` value to true or false. By default, Enable Zooming value is set to true.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor  EnableZooming="false"/>
     
{% endhighlight %}

{% highlight C# %}
   
     editor.EnableZooming = false;

{% endhighlight %}

{% endtabs %}

## Maximum ZoomLevel

You can set the image maximum zoom level with the help of `MaximumZoomLevel` property.

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

Image editor control provides support for panning. Image editor allows you to pan the image with two fingers or single finger by setting image editor PanningMode.

The following properties are used in the panning.

* `SingleFinger` – You can zoom or pan the image with single finger but shapes and text selection cannot be performed with this mode.

* `TwoFinger` – You can zoom or pan the image with two finger also shapes and text selection can be performed with this mode.

By default, PanningMode value set to `TwoFinger`.

{% tabs %}

{% highlight XAML %}

    <imageeditor:SfImageEditor  EnableZooming="true" PanningMode="TwoFinger"/>

{% endhighlight %}

{% highlight C# %}

editor.PanningMode = PanningMode.TwoFinger;

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/zoom.gif)


