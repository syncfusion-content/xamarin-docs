---
layout: post
title: Setting Displaying Text of DigitalGauge
description: Learn how to set Display Text in DigitalGauge
platform: Xamarin
control: DigitalGauge
documentation: ug
---

# Setting Displaying Text

The Digital Characters in the SfDigitalGauge is viewed in different types of segments. These digital characters are set to the SfDigitalGauge through the `Value` property of type string.

{% tabs %}

{% highlight c# %}

	digitalgauge.CharacterType=CharacterType.EightCrossEightDotMatrix;
	digitalgauge.Value=”@ # $ &”;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge" CharacterType="EightCrossEightDotMatrix" Value="{Binding}" />

{% endhighlight %}

{% endtabs %}


![](Getting-Started_images/specialcharacter.png)