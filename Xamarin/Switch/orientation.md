---
layout: post
title: Orientation in Xamarin Switch Control | Syncfusion
description: Learn about orientation support in the Syncfusion Xamarin Switch (SfSwitch) control and its elements.
platform: Xamarin
control: Switch
documentation: ug
---

# Orientation in Xamarin Switch (SfSwitch)

The Switch control allows you to change the default [`Orientation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_Orientation).

## Horizontal Orientation

By default, the switch is displayed horizontally. You can explicitly set the [`Orientation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_Orientation) as shown in the code example below.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch Orientation="Horizontal" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.Orientation = SwitchOrientation.Horizontal;

{% endhighlight %}

{% endtabs %}

![Switch control with horizontal orientation](images/orientation.png)

## Vertical Orientation
To display the switch control vertically, set the [`Orientation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_Orientation) to `Vertical`, as demonstrated in the following code example.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch Orientation="Vertical" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.Orientation = SwitchOrientation.Vertical;

{% endhighlight %}

{% endtabs %}

![Switch control with vertical orientation](images/vertical.png)
