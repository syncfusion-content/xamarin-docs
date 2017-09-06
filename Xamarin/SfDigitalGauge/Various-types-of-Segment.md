---
layout: post
title: Character type in DigitalGauge
description: Learn how to define character type in DigitalGauge
platform: Xamarin
control: DigitalGauge
documentation: ug
---

# Various types of Segment

The Digital Characters can be drawn in 4 different segments as follows.
 
1. Seven

2. Fourteen

3. Sixteen

4. EightCrossEightDotMatrix

N>  SegmentSeven is the default CharacterType in the SfDigitalGauge.

## Seven Segment

The seven segment type is capable of displaying numbers and few upper case letters efficiently.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digital"  CharacterType="SegmentSeven" />

{% endhighlight %}

{% highlight c# %}

	digital.CharacterType = CharacterType.SegmentSeven;

{% endhighlight %}

{% endtabs %}

## Fourteen Segment

The fourteen segment type is capable of displaying numbers, alphabets efficiently.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digital" CharacterType="SegmentFourteen" />

{% endhighlight %}

{% highlight c# %}

	digital.CharacterType = CharacterType.SegmentFourteen;

{% endhighlight %}


{% endtabs %}

 
## Sixteen Segment

The sixteen segment type is capable of displaying numbers, alphabets with clear display.
 
{% tabs %} 

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digital"  CharacterType="SegmentSixteen" />

{% endhighlight %}
 
{% highlight c# %}

	digital.CharacterType = CharacterType.SegmentSixteen;

{% endhighlight %}

{% endtabs %}

## EightCrossEightDotMatrix Segment

The dot matrix segment type is capable of displaying numbers, alphabets and any special character efficiently with clear display.

{% tabs %}

{% highlight xaml %}

	<gauge:SfDigitalGauge x:Name="digital"  CharacterType="EightCrossEightDotMatrix"  />

{% endhighlight %}

{% highlight c# %}

	digital.CharacterType = CharacterType.EightCrossEightDotMatrix;

{% endhighlight%}

{% endtabs %}

![](Getting-Started_images/segment.png)

