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

{% highlight c# %}

sfDigitalGauge.CharacterType = CharacterType.SegmentSeven;

{% endhighlight %}

![](Getting-Started_images/SegmentSeven.png)

## Fourteen Segment

{% highlight c# %}

sfDigitalGauge.CharacterType = CharacterType.SegmentFourteen;

{% endhighlight %}

![](Getting-Started_images/SegmentFourteen.png)
 
## Sixteen Segment
 
{% highlight c# %}

sfDigitalGauge.CharacterType = CharacterType.SegmentSixteen;

{% endhighlight %}

![](Getting-Started_images/SegmentSixteen.png)

## EightCrossEightDotMatrix Segment

{% highlight c# %}

sfDigitalGauge.CharacterType = CharacterType.EightCrossEightDotMatrix;

{% endhighlight%}

![](Getting-Started_images/SegmentMatrix.png)

