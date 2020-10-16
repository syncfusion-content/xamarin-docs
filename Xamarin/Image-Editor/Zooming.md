---
layout: post
title: Zooming and Panning operations in Syncfusion SfImageEditor
description: Learn how to perform Zooming and panning in the image in SfImageEditor control for Xamarin.Forms platform
platform: xamarin.forms
control: ImageEditor
documentation: ug
---

# Zooming in SfImageEditor

The image editor control provides support to zoom and pan actions over an image.

The following properties are used for zooming feature of the image editor control:

* EnableZooming
* Maximum ZoomLevel
* PanningMode

## Enable zooming

You can enable or disable the zooming functionality by setting the [`EnableZooming`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_EnableZooming) value to true or false. By default, the `EnableZooming` value is set to true.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor  EnableZooming="false"/>
     
{% endhighlight %}

{% highlight C# %}
   
     editor.EnableZooming = false;

{% endhighlight %}

{% endtabs %}

### Zoom level

Programmatically, you can zoom the loaded image without any interaction by setting a value to [`ZoomLevel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_ZoomLevel) property. At the same time, you can get the information about whether the image is zoomed or not by accessing the [`IsImageZoomed`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_IsImageZoomed) property in image editor.

{% tabs %}

{% highlight XAML %}
  
    <editor:SfImageEditor x:Name="editor" Source="{Binding Image}" ImageLoaded="SfImageEditor_ImageLoaded"/>
     
{% endhighlight %}

{% highlight C# %}

            SfImageEditor editor = new SfImageEditor();
            editor.Source = ImageSource.FromResource("XFormsUG.RoadView.jpeg");
            editor.ImageLoaded += SfImageEditor_ImageLoaded;
            this.Content = editor;
   
        private void SfImageEditor_ImageLoaded(object sender, ImageLoadedEventArgs args)
        {
            editor.ZoomLevel = 3;
        }

{% endhighlight %}

{% endtabs %}

## Maximum zoom level

You can set the maximum zoom level to image using the [`MaximumZoomLevel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_MaximumZoomLevel) property.

{% tabs %}

{% highlight XAML %}
  
    <imageeditor:SfImageEditor EnableZooming="true"  MaximumZoomLevel="8"/>
     
{% endhighlight %}

{% highlight C# %}

     editor.EnableZooming = true;
     editor.MaximumZoomLevel = 8;

{% endhighlight %}

{% endtabs %}

## Panning mode

The image editor control provides support for panning and allows to pan the image with two fingers or single finger by setting the [`PanningMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_PanningMode).

The following properties are used for panning:

* `SingleFinger`: Zooms or pans the image with single finger, but shapes and text selection cannot be performed with this mode.
* `TwoFinger`: Zooms or pans the image with two finger. The shapes and text selection can be performed with this mode.

By default, the [`PanningMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_PanningMode) value is set to `TwoFinger`.

{% tabs %}

{% highlight XAML %}

    <imageeditor:SfImageEditor  EnableZooming="true" PanningMode="TwoFinger"/>

{% endhighlight %}

{% highlight C# %}

editor.PanningMode = PanningMode.TwoFinger;

{% endhighlight %}

{% endtabs %}

## See also

[How to create zoom able image in Xamarin.Forms using SfImageEditor](https://www.syncfusion.com/kb/9379/how-to-create-zoomable-image-in-xamarin-forms-using-sfimageeditor)
