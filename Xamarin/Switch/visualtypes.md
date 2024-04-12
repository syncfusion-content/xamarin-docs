---
layout: post
title: Visual Types in Xamarin Switch Control | Syncfusion
description: Learn here all about visual types support in Syncfusion Xamarin Switch (SfSwitch) control, its elements and more.
platform: xamarin
control: Switch
documentation: ug
---

# Visual Types in Xamarin Switch (SfSwitch)

[`SfSwitch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html) supports customization using built-in [`visual types`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_VisualType). The [`visual types`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_VisualType) based on device platform are listed as follows.

* Android – [`Material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Material) 
* iOS – [`Cupertino`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Cupertino)
* Windows – [`Fluent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Fluent)

## Default

This is the default value set for visual type.

![Switch control is having default visual type in Xamarin.Forms](images/xamarin.forms-switch-default-visual-type.png)

N> If you set [`default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Default), the visual type will be internally changed based on the device platform.

## Material

[`Material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Material) visual type brings the appearance based on [`material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Material) guidelines. The following code example demonstrates how to define [`material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Material) visual type.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch VisualType="Material" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Material;

{% endhighlight %}

{% endtabs %}

![Switch control is having material visual type in Xamarin.Forms](images/xamarin.forms-switch-material-visual-type.png)

## Cupertino

[`Cupertino`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Cupertino) visual type brings the appearance based on [`Cupertino`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Cupertino) guidelines. The following code example demonstrates how to define [`Cupertino`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Cupertino) visual type.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch VisualType="Cupertino" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Cupertino;

{% endhighlight %}

{% endtabs %}

![Switch control is having cupertino visual type in Xamarin.Forms](images/xamarin.forms-switch-cupertino-visual-type.png)

## Fluent

[`Fluent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Fluent) visual type brings the appearance based on[`Fluent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Fluent) guidelines. The following code example demonstrates how to define [`Fluent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Fluent) visual type.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch VisualType="Fluent" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Fluent;

{% endhighlight %}

{% endtabs %}

![Switch control is having fluent visual type in Xamarin.Forms](images/xamarin.forms-switch-fluent-visual-type.png)

## Custom

[`Custom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Custom) type will allow you to customize the control, where you can handle the size, colors, images etc. of the control. Refer to this [`documentation`](https://help.syncfusion.com/xamarin/sfswitch/customization).

