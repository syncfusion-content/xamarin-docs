---
layout: post
title: Customization in Syncfusion Signature Pad Xamarin.Forms
description: This section explains the details about the customization of Syncfusion Signature Pad control for Xamarin.Forms
platform: xamarin
control: SfSignaturePad
documentation: ug
---

# Customization in Signature Pad

The `Signature Pad` control supports to customize the stroke color and stroke width using the following properties:

## Stroke color

The color of the signature can be customized using the `StrokeColor` property.

{% tabs %}

{% highlight xaml %}

    <sign:SfSignaturePad HeightRequest="250" StrokeColor="Red"/>

{% endhighlight %}

{% highlight c# %}

    SfSignaturePad sign = new SfSignaturePad();
    sign.StrokeColor = Color.Red;
    sign.HeightRequest = 250;
    this.Content = sign;
    
{% endhighlight %}

{% endtabs %}

![stroke color](images/StrokeColor.png)

## Stroke width

The stroke width of the signature can be customized by setting the MinimumStrokeWidth and MaximumStrokeWidth API. The MinimumStrokeWidth defines the minimum thickness of the stroke that can be drawn and the MaximumStrokeWidth defines the maximum thickness the stroke can draw based on the speed and impression we provide through gesture.

N> The default value of `MinimumStrokeWidth` is 0.08 and `MaximumStrokeWidth` is 5.

{% tabs %}

{% highlight xaml %}

     <sign:SfSignaturePad HeightRequest="250" 
                          MinimumStrokeWidth="1" 
                          MaximumStrokeWidth="15"/>

{% endhighlight %}

{% highlight c# %}

    SfSignaturePad sign = new SfSignaturePad();
    sign.MinimumStrokeWidth = 1;
    sign.MaximumStrokeWidth = 4;
    sign.HeightRequest = 250;
    this.Content = sign;
    
{% endhighlight %}

{% endtabs %}

![Stroke width](images/StrokeWidth.png)

[Sample link](https://github.com/SyncfusionExamples/xamarin-sfsignaturepad-examples/tree/master/Samples/SfSignaturePadCustomization)
