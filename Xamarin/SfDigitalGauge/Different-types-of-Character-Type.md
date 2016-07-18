---
layout: post
title: Character type in DigitalGauge
description: Learn how to define character type in DigitalGauge
platform: Xamarin
control: DigitalGauge
documentation: ug
---

# Different types of Character Type

The Digital Characters can be drawn in 4 different segments as follows.
 
1. Seven

2. Fourteen

3. Sixteen

4. EightCrossEightDotMatrix

N> By default, SegmentSeven is the default CharacterType in the SfDigitalGauge.

## Seven Segment

{% tabs %}

{% highlight c# %}

	digitalgauge.CharacterType = CharacterType.SegmentSeven;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge"  CharacterType="SegmentSeven" />

{% endhighlight %}

{% endtabs %}

## Fourteen Segment

{% tabs %}

{% highlight c# %}

	digitalgauge.CharacterType = CharacterType.SegmentFourteen;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge" CharacterType="SegmentFourteen" />

{% endhighlight %}

{% endtabs %}

 
## Sixteen Segment
 
{% tabs %} 
 
{% highlight c# %}

	digitalgauge.CharacterType = CharacterType.SegmentSixteen;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge"  CharacterType="SegmentSixteen" />

{% endhighlight %}

{% endtabs %}

## EightCrossEightDotMatrix Segment

{% tabs %}

{% highlight c# %}

	digitalgauge.CharacterType = CharacterType.EightCrossEightDotMatrix;

{% endhighlight%}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digitalgauge"  CharacterType="EightCrossEightDotMatrix"  />

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/segment.png)

