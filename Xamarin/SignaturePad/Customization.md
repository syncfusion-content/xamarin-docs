---
layout: post
title: Customization in Syncfusion Signature Pad Xamarin.Forms
description: This section explains the details about the customization of Syncfusion Signature Pad control for Xamarin.Forms
platform: xamarin
control: SfSignaturePad
documentation: ug
---

# Customization in Signature Pad

The Signature Pad control supports to customize the stroke color and stroke width using the following API.

## Stroke color

The color of the stroke drawn can be customized using the `StrokeColor` API.

{% tabs %}

{% highlight xaml %}

    <signature:SfSignaturePad HeightRequest="250" StrokeColor="Red"/>

{% endhighlight %}

{% highlight c# %}

    SfSignaturePad signature = new SfSignaturePad();
    signature.StrokeColor = Color.Red;
    signature.HeightRequest = 250;
    this.Content = signature;
    
{% endhighlight %}

{% endtabs %}

![stroke color](images/StrokeColor.png)

## Stroke width

The width of the stroke drawn can be customized by setting the `MinimumStrokeWidth` and `MaximumStrokeWidth` API. The `MinimumStrokeWidth` defines the minimum thickness of the stroke that can be drawn and the `MaximumStrokeWidth` defines the maximum thickness the stroke can draw based on the speed and impression we provide through gesture.

N> The default value of `MinimumStrokeWidth` is 0.08 and `MaximumStrokeWidth` is 5.

{% tabs %}

{% highlight xaml %}

     <signature:SfSignaturePad HeightRequest="250" 
                          MinimumStrokeWidth="1" 
                          MaximumStrokeWidth="15"/>

{% endhighlight %}

{% highlight c# %}

    SfSignaturePad signature = new SfSignaturePad();
    signature.MinimumStrokeWidth = 1;
    signature.MaximumStrokeWidth = 4;
    signature.HeightRequest = 250;
    this.Content = signature;
    
{% endhighlight %}

{% endtabs %}

![Stroke width](images/StrokeWidth.png)

N> View [sample](https://github.com/SyncfusionExamples/xamarin-sfsignaturepad-examples/tree/master/Samples/SfSignaturePadCustomization) in GitHub