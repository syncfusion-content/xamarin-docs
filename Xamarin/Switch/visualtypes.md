---
layout: post
title: Visual Types in Xamarin Switch Control | Syncfusion
description: Explore the various visual types supported by the Syncfusion Xamarin Switch (SfSwitch) control, including elements and customization options.
platform: Xamarin
control: Switch
documentation: ug
---

# Visual Types in Xamarin Switch (SfSwitch)

The [`SfSwitch`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html) control supports customization through built-in [`visual types`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_VisualType). The visual types available based on the device platform are listed below:

- Android – [`Material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Material)
- iOS – [`Cupertino`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Cupertino)
- Windows – [`Fluent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Fluent)

## Default

This is the default visual type setting.

![Switch control with default visual type](images/default.png)

> **Note:** When set to [`Default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Default), the visual type changes internally based on the device platform.

## Material

The [`Material`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Material) visual type provides an appearance based on material design guidelines. The following code example demonstrates how to define the `Material` visual type.
{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch VisualType="Material" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Material;

{% endhighlight %}

{% endtabs %}

![Switch control with material visual type](images/material.png)

## Cupertino

The [`Cupertino`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Cupertino) visual type provides an appearance based on Cupertino design guidelines. See the code example below to define the `Cupertino` visual type.
{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch VisualType="Cupertino" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Cupertino;

{% endhighlight %}

{% endtabs %}

![Switch control with Cupertino visual type](images/cupertino.png)

## Fluent

The [`Fluent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Fluent) visual type offers an appearance based on Fluent design guidelines. The following code example shows how to define the `Fluent` visual type.
{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch VisualType="Fluent" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Fluent;

{% endhighlight %}

{% endtabs %}

![Switch control with fluent visual type](images/fluent.png)

## Custom

The [`Custom`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.VisualType.html#Syncfusion_XForms_Buttons_VisualType_Custom) type allows you to customize the control, including aspects like size, colors, and images. Refer to this [documentation](https://help.syncfusion.com/xamarin/sfswitch/customization) for more details.
