---
layout: post
title: Orientation in Xamarin Switch control | Syncfusion
description: Learn here all about Orientation support in Syncfusion Xamarin Switch (SfSwitch) control, its elements and more.
platform: Xamarin
control: Switch
documentation: ug
---

# Orientation in Xamarin Switch (SfSwitch)

The switch control provides options to change the default [`orientation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_Orientation).

## Horizontal 

By default, it is displayed horizontally. You can also define the [`orientation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_Orientation) as demonstrated in the following code example.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch Orientation="Horizontal" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.Orientation = SwitchOrientation.Horizontal;

{% endhighlight %}

{% endtabs %}

![switch conrol has horizontal orientation](images/orientation.png)

## Vertical

To view the switch control vertically, you can define the vertical [`orientation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_Orientation)as demonstrated in the following code example.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch Orientation="Vertical" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.Orientation = SwitchOrientation.Vertical;

{% endhighlight %}

{% endtabs %}

![switch conrol has vertical orientation](images/vertical.png)
