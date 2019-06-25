---
layout: post
title: Orientation in Syncfusion SfSwitch Xamarin.Forms.
description: Explaining about types of orientation in SfSwitch.
platform: Xamarin
control: Switch
documentation: ug
---

# Orientation

The switch control provides options to change the default orientation.

## Horizontal 

By default, it is displayed horizontally. You can also define the orientation as demonstrated in the following code example.

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

To view the switch control vertically, you can define the vertical orientation as demonstrated in the following code example.

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