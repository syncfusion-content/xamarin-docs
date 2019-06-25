---
layout: post
title: Visual types in Syncfusion SfSwitch Xamarin.Forms.
description: Explaining about visual types in SfSwitch.
platform: Xamarin
control: Switch
documentation: ug
---

## Visual Types

SfSwitch supports customization using built in visual types. The visual types based on the device platform is listed below.

* Android – Material 
* iOS – Cupertino
* Windows – Fluent

### Default

This is the default value set for visual type. 

![switch conrol having default visual type](images/default.png)

N> If we set default, the visual type is internally changed based on the device platform.

### Material

Material visual type brings in the appearance based on material guidelines. The below code example shows you how to define material visual type.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch VisualType="Material" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Material;

{% endhighlight %}

{% endtabs %}

![switch conrol having material visual type](images/material.png)

### Cupertino

Cupertino visual type brings in the appearance based on Cupertino guidelines. The below code example shows you how to Cupertino visual type. 

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch VisualType="Cupertino" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Cupertino;

{% endhighlight %}

{% endtabs %}

![switch conrol having cupertino visual type](images/cupertino.png)

### Fluent

Fluent visual type brings in the appearance based on Fluent guidelines. The below code example shows you how to Fluent visual type.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch VisualType="Fluent" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.VisualType = VisualType.Fluent;

{% endhighlight %}

{% endtabs %}

![switch conrol having fluent visual type](images/fluent.png)

### Custom

Custom type will allow you to customize the control where you can handle the size, colors, images etc. of the control. Please refer [`here`]().