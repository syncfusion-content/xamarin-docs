---
layout: post
title: Character Types in Xamarin Digital Gauge control | Syncfusion<sup>&reg;</sup>
description: Learn here all about Character Types support in Syncfusion<sup>&reg;</sup> Xamarin Digital Gauge (SfDigitalGauge) control and more.
platform: Xamarin
control: DigitalGauge
documentation: ug
---

# Character Types in Xamarin Digital Gauge (SfDigitalGauge)

The digital characters can be drawn in the following four different segments:

•	Seven

•	Fourteen

•	Sixteen

•	EightCrossEightDotMatrix

## Seven segment

The seven-segment type is capable of displaying numbers and a few uppercase letters efficiently.

{% tabs %}

{% highlight xaml %}

    <gauge:SfDigitalGauge Value="SYNCFUSION" SegmentStrokeWidth="4" 
                          HeightRequest="100"  WidthRequest="340"
                          DisabledSegmentAlpha="25" DisabledSegmentColor="Gray"
                          CharacterHeight="90" CharacterWidth="25" 
                          HorizontalOptions="Center" VerticalOptions="Center"
                          CharacterType="SegmentSeven" 
                         CharacterStrokeColor="#146CED"/>

{% endhighlight %}

{% highlight c# %}

           SfDigitalGauge digital = new SfDigitalGauge();

            digital.HeightRequest = 100;

            digital.WidthRequest = 340;

            digital.Value = "SYNCFUSION";

            digital.CharacterHeight = 90;

            digital.CharacterWidth = 25;

            digital.HorizontalOptions = LayoutOptions.Center;

            digital.VerticalOptions = LayoutOptions.Center;

            digital.SegmentStrokeWidth = 4;

            digital.CharacterType = CharacterType.SegmentSeven;

            digital.DisabledSegmentAlpha = 25;

            digital.CharacterStrokeColor = Color.FromRgb(20, 108, 237);

            digital.DisabledSegmentColor = Color.Gray;

{% endhighlight %}

{% endtabs %}

![Character type support in Xamarin.Forms Digital Gauge](CharacterTypes_images/CharacterTypes_img1.png)

## Fourteen segment

The fourteen-segment type is capable of displaying numbers and alphabet efficiently.

![Fourteen segment in Xamarin.Forms Digital Gauge](CharacterTypes_images/CharacterTypes_img2.png)

## Sixteen segment

The sixteen-segment type is capable of displaying numbers and alphabet clearly.

![Sixteen segment in Xamarin.Forms Digital Gauge](CharacterTypes_images/CharacterTypes_img3.png)

## EightCrossEightDotMatrix segment

The dot matrix segment type is capable of displaying numbers, alphabet, and special characters efficiently.

![Dot matrix segment in Xamarin.Forms Digital Gauge](CharacterTypes_images/CharacterTypes_img4.png)
