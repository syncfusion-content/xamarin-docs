---
layout: post
title: Character type in DigitalGauge
description: Learn how to define character type in DigitalGauge
platform: Xamarin
control: DigitalGauge
documentation: ug
---

# CharacterType

The Digital Characters can be drawn in 4 different segments as follows.
 
1. Seven

2. Fourteen

3. Sixteen

4. EightCrossEightDotMatrix

N> By default, SegmentSeven is the default CharacterType in the Digital Gauge.

## Seven Segment

{% tabs %}

{% highlight c# %}

	sfDigitalGauge.CharacterType = CharacterType.SegmentSeven;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="sfdigitalgauge"  CharacterType="SegmentSeven" />

{% endhighlight %}

{% endtabs %}

## Fourteen Segment

{% tabs %}

{% highlight c# %}

	sfDigitalGauge.CharacterType = CharacterType.SegmentFourteen;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="sfdigitalgauge" CharacterType="SegmentFourteen" />

{% endhighlight %}

{% endtabs %}

 
## Sixteen Segment
 
{% tabs %} 
 
{% highlight c# %}

	sfDigitalGauge.CharacterType = CharacterType.SegmentSixteen;

{% endhighlight %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="sfdigitalgauge"  CharacterType="SegmentSixteen" />

{% endhighlight %}

{% endtabs %}

## EightCrossEightDotMatrix Segment

{% tabs %}

{% highlight c# %}

	sfDigitalGauge.CharacterType = CharacterType.EightCrossEightDotMatrix;

{% endhighlight%}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="sfdigitalgauge"  CharacterType="EightCrossEightDotMatrix"  />

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/segment.png)

