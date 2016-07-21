---
layout: post
title: Setting Displaying Text of DigitalGauge
description: Learn how to set Display Text in DigitalGauge
platform: Xamarin
control: DigitalGauge
documentation: ug
---

# Display Special Characters

The special characters in the SfDigitalGauge is viewed in different types of segments. These special characters are set to the SfDigitalGauge through the `Value` property of type string.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge" CharacterType="EightCrossEightDotMatrix" Value="{Binding}" />

{% endhighlight %}

{% highlight c# %}

	digitalgauge.CharacterType=CharacterType.EightCrossEightDotMatrix;
	digitalgauge.Value=”@ # $ &”;

{% endhighlight %}

{% endtabs %}


![](Getting-Started_images/specialcharacter.png)