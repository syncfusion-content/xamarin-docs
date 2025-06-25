---
layout: post
title: Customization in Xamarin SignaturePad Control | Syncfusion
description: Explore the customization capabilities of Syncfusion Xamarin SignaturePad (SfSignaturePad) control.
platform: Xamarin
control: SfSignaturePad
documentation: ug
---

# Customization in Xamarin SignaturePad (SfSignaturePad)

The SignaturePad control supports customization of stroke color and stroke width using the following APIs.

## Stroke Color

The color of the stroke drawn can be customized using the [`StrokeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_StrokeColor) API.

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

![Stroke Color Customization](images/StrokeColor.png)

## Stroke Width

The width of the stroke drawn can be customized by setting the [`MinimumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MinimumStrokeWidth) and [`MaximumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MaximumStrokeWidth) APIs. The [`MinimumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MinimumStrokeWidth) defines the minimum thickness of the stroke, while the [`MaximumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MaximumStrokeWidth) defines the maximum thickness the stroke can have based on the speed and impression provided through gesture.

> Note: The default value of [`MinimumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MinimumStrokeWidth) is 0.08 and [`MaximumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MaximumStrokeWidth) is 5.

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

![Stroke Width Customization](images/StrokeWidth.png)

> Note: View the [sample](https://github.com/SyncfusionExamples/xamarin-sfsignaturepad-examples/tree/master/Samples/SfSignaturePadCustomization) on GitHub.
