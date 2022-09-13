---
layout: post
title: Customization in Xamarin SignaturePad control | Syncfusion
description: Learn here all about Customization support in Syncfusion Xamarin SignaturePad (SfSignaturePad) control and more.
platform: xamarin
control: SfSignaturePad
documentation: ug
---

# Customization in Xamarin SignaturePad (SfSignaturePad)

The Signature Pad control supports to customize the stroke color and stroke width using the following API.

## Stroke color

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

![stroke color](images/StrokeColor.png)

## Stroke width

The width of the stroke drawn can be customized by setting the [`MinimumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MinimumStrokeWidth) and [`MaximumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MaximumStrokeWidth) API. The [`MinimumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MinimumStrokeWidth) defines the minimum thickness of the stroke that can be drawn and the [`MaximumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MaximumStrokeWidth) defines the maximum thickness the stroke can draw based on the speed and impression we provide through gesture.

N> The default value of [`MinimumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MinimumStrokeWidth) is 0.08 and [`MaximumStrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_MaximumStrokeWidth) is 5.

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
