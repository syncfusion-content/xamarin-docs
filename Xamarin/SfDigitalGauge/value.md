---
layout: post
title: Value of DigitalGauge
description: Learn how to add  value to DigitalGauge
platform: Xamarin
control: DigitalGauge
documentation: ug
---

# Value

The Digital Characters in the Digital Gauge is viewed in different types of segments. These digital characters are set to the Digital Gauge through the Value property of type string.

{% tabs %}

{% highlight c# %}

	sfDigitalGauge.CharacterType=CharacterType.EightCrossEightDotMatrix;
	sfDigitalGauge.Value=”@ # $ &”;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="sfdigitalgauge" CharacterType="EightCrossEightDotMatrix" Value="@ # $ &" />

{% endhighlight %}

{% endtabs %}


![](Getting-Started_images/specialcharacter.png)