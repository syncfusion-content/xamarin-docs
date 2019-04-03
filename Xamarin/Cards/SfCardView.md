---
layout: post
title: SfCardView in Essential Syncfusion.Xamarin.Forms Cards
description: Customization of SfCardView.
platform: xamarin
control: Cards
documentation: ug
---

## Indicator customization

Indicators are used to indicate the state or level of something.

{% tabs %} 

{% highlight xaml %}

    <cards:SfCardView x:Name="cardView" IndicatorColor="Cyan" IndicatorThickness="12" IndicatorPosition="Left" />

{% endhighlight %}

{% highlight C# %}

SfCardView cardView = new SfCardView();
cardView.IndicatorThickness = 12;
cardView.IndicatorPosition = IndicatorPosition.Left;
cardView.IndicatorColor = Color.Cyan;

{% endhighlight %}

{% endtabs %}

![Indicator in Xamarin.Forms SfCardLayout](cardview-customization_images/indicator.png)

Refer to this [documentation](https://help.syncfusion.com/xamarin/cards/indicator) to learn more about the options available in [`Cards`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.Cards.XForms.SfCardView.html) to customize the indicator.

## FadeOutOnSwiping

FadeOutOnSwiping can be enabled when the card view needs to be faded with respect to swiping.

{% tabs %} 

{% highlight xaml %}

    <cards:SfCardView x:Name="cardView" FadeOutOnSwiping="true"/>
 
{% endhighlight %}

{% highlight C# %}

SfCardView cardView = new SfCardView(); 
cardView.FadeOutOnSwiping = true;

{% endhighlight %}

{% endtabs %}

You can find the complete getting started sample from this [link](https://github.com/SyncfusionExamples/xamarin.forms-cards).

