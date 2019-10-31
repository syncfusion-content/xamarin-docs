---
layout: post
title: Visual types in Syncfusion SfSwitch Xamarin.Forms.
description: Explaining about visual types in SfSwitch.
platform: Xamarin
control: Switch
documentation: ug
---

# Visual Types

SfSwitch supports customization using built-in visual types. The visual types based on device platform are listed as follows.

* Android – Material 
* iOS – Cupertino
* Windows – Fluent

## Default

This is the default value set for visual type.

![switch conrol is having default visual type](images/default.png)

N> If you set default, the visual type will be internally changed based on the device platform.

## Material

Material visual type brings the appearance based on material guidelines. The following code example demonstrates how to define material visual type.

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

Cupertino visual type brings the appearance based on Cupertino guidelines. The following code example demonstrates how to define Cupertino visual type.

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

Fluent visual type brings the appearance based on Fluent guidelines. The following code example demonstrates how to define Fluent visual type.

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

