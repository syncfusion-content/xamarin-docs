---
layout: post
title: Character Dimensions of DigitalGauge
description: Learn how set the Character Dimensions in DigitalGauge
platform: Xamarin.Forms
control: DigitalGauge
documentation: ug
---

# Setting Character Dimensions

The Digital Characters size can be scaled using `CharacterHeight` and `CharacterWidth` properties in the SfDigitalGauge control.

## CharacterHeight

The value of the Digital Characters is scaled by altering the height of the digital characters. It is achieved by setting the `CharacterHeight` property in the SfDigitalGauge.

{% tabs %}

{% highlight c# %}

	digitalgauge.CharacterHeight = 50;

{% endhighlight  %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge" CharacterHeight="50" />

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/characterheight.png)

## CharacterWidth

The value of the Digital Characters is scaled by altering the width of the digital characters. It is achieved by setting the `CharacterWidth` property.

{% tabs %}

{% highlight c# %}

	digitalgauge.CharacterWidth = 50;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge" CharacterWidth="50" />

{% endhighlight %}

{% endtabs %}


![](Getting-Started_images/characterwidth.png)