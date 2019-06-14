---
layout: post
title: Orientation in Syncfusion SfSwitch Xamarin.Forms.
description: Explaining about types of orientation in SfSwitch.
platform: Xamarin
control: Switch
documentation: ug
---

## Orientation

Switch control provides option for you to change the default alignment. 

### Horizontal 

By default, it is displayed horizontally. You can also define the Orientation as shown in the below code example.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfSwitch Orientation="Horizontal" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.Orientation = SwitchOrientation.Horizontal;

{% endhighlight %}

{% endtabs %}

![switch conrol having horizontal orientation](images/horizontal.png)

### Vertical

To view the switch button in vertical direction, you can define the Vertical Orientation as shown in the below code example.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfSwitch Orientation="Vertical" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.Orientation = SwitchOrientation.Vertical;

{% endhighlight %}

{% endtabs %}

![switch conrol having vertical orientation](images/vertical.png)