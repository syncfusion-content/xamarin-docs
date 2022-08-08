---
layout: post
title: Visual Types in Xamarin Switch control | Syncfusion
description: Learn here all about Visual Types support in Syncfusion Xamarin Switch (SfSwitch) control, its elements and more.
platform: Xamarin
control: Switch
documentation: ug
---

# Visual Types in Xamarin Switch (SfSwitch)

[`SfSwitch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html) supports customization using built-in visual types. The visual types based on device platform are listed as follows.

* Android – [`Material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Material) 
* iOS – [`Cupertino`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Cupertino)
* Windows – [`Fluent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Fluent)

## Default

This is the default value set for visual type.

![switch conrol is having default visual type](images/default.png)

N> If you set default, the visual type will be internally changed based on the device platform.

## Material

[`Material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Material) visual type brings the appearance based on material guidelines. The following code example demonstrates how to define material visual type.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch VisualType="Material" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Material;

{% endhighlight %}

{% endtabs %}

![switch conrol is having material visual type](images/material.png)

## Cupertino

[`Cupertino`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Cupertino) visual type brings the appearance based on Cupertino guidelines. The following code example demonstrates how to define Cupertino visual type.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch VisualType="Cupertino" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Cupertino;

{% endhighlight %}

{% endtabs %}

![switch conrol is having cupertino visual type](images/cupertino.png)

## Fluent

[`Fluent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Fluent) visual type brings the appearance based on Fluent guidelines. The following code example demonstrates how to define Fluent visual type.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch VisualType="Fluent" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Fluent;

{% endhighlight %}

{% endtabs %}

![switch conrol is having fluent visual type](images/fluent.png)

## Custom

Custom type will allow you to customize the control, where you can handle the size, colors, images etc. of the control. Refer to this [`documentation`](https://help.syncfusion.com/xamarin/sfswitch/customization).

