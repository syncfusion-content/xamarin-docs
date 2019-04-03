---
layout: post
title: SfCardLayout in Essential Syncfusion.Xamarin.Forms Cards
description: Customization of SfCardLayout and SfCardView.
platform: xamarin
control: Cards
documentation: ug
---

# Customization in CardLayout

## ShowSwipedCard

ShowSwipedCard can be enabled to show the swiped cards at the edge of card layout.

{% tabs %} 

{% highlight xaml %}

<cards:SfCardLayout ShowSwipedCard="true">
</cards:SfCardLayout>
 
{% endhighlight %}

{% highlight C# %}

SfCardLayout cardLayout = new SfCardLayout();
cardLayout.ShowSwipedCard = true;

this.Content = cardLayout;

{% endhighlight %}

{% endtabs %}

![ShowSwipedCard in Xamarin.Forms SfCardLayout](cardlayout-customization_images/showswipedcard.png)

## VisibleCardIndex

VisibleCardIndex is used when given index of the card to be displayed in front of the card layout.

{% tabs %} 

{% highlight xaml %}

<cards:SfCardLayout VisibleCardIndex="1">
</cards:SfCardLayout>
 
{% endhighlight %}

{% highlight C# %}

SfCardLayout cardLayout = new SfCardLayout();
cardLayout.VisibleCardIndex = 1;

this.Content = cardLayout;

{% endhighlight %}

{% endtabs %}

![VisibleCardIndex in Xamarin.Forms SfCardLayout](cardlayout-customization_images/showswipedcard.png)

## SwipeDirection

The SwipeDirection property indicates the swiping direction (left or right).

{% tabs %} 

{% highlight xaml %}

<cards:SfCardLayout SwipeDirection="Right">
</cards:SfCardLayout>
 
{% endhighlight %}

{% highlight C# %}

SfCardLayout cardLayout = new SfCardLayout();
cardLayout.SwipeDirection = CardSwipeDirection.Right;

this.Content = cardLayout;

{% endhighlight %}

{% endtabs %}

![SwipeDirection in Xamarin.Forms SfCardLayout](cardlayout-customization_images/swipedirection.png)

You can find the complete getting started sample from this [link](https://github.com/SyncfusionExamples/xamarin.forms-cards).

# Customization in CardView

## Indicator customization

Indicators are used to indicate the state or level of something.

{% tabs %} 

{% highlight xaml %}

    <cards:SfCardView IndicatorColor="Cyan" IndicatorThickness="12" IndicatorPosition="Left" />

{% endhighlight %}

{% highlight C# %}

SfCardView cardView = new SfCardView();
cardView.IndicatorThickness = 12;
cardView.IndicatorPosition = IndicatorPosition.Left;
cardView.IndicatorColor = Color.Cyan;

{% endhighlight %}

{% endtabs %}

![Indicator in Xamarin.Forms SfCardLayout](cardview-customization_images/indicator.png)

## FadeOutOnSwiping

FadeOutOnSwiping can be enabled when the card view needs to be faded with respect to swiping.

{% tabs %} 

{% highlight xaml %}

    <cards:SfCardView FadeOutOnSwiping="true"/>
 
{% endhighlight %}

{% highlight C# %}

SfCardView cardView = new SfCardView(); 
cardView.FadeOutOnSwiping = true;

{% endhighlight %}

{% endtabs %}

You can find the complete getting started sample from this [link](https://github.com/SyncfusionExamples/xamarin.forms-cards).



