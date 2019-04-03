---
layout: post
title: SfCardLayout in Essential Syncfusion.Xamarin.Forms Cards
description: Customization of SfCardLayout.
platform: xamarin
control: Cards
documentation: ug
---

## ShowSwipedCard

ShowSwipedCard can be enabled to show swiped cards at the edge of card layout.

{% tabs %} 

{% highlight xaml %}

<cards:SfCardLayout ShowSwipedCard="true">
</cards:SfCardLayout>
 
{% endhighlight %}

{% highlight C# %}

SfCardLayout cardLayout = new SfCardLayout();
cardlayout.ShowSwipedCard = true;

this.Content = cardLayout;

{% endhighlight %}

{% endtabs %}

![ShowSwipedCard in Xamarin.Forms SfCardLayout](cardlayout-customization_images/showswipedcard.png)

## VisibleCardIndex

VisibleCardIndex is used when the given index of the card to be displayed in front of the card layout.

{% tabs %} 

{% highlight xaml %}

<cards:SfCardLayout VisibleCardIndex="1">
</cards:SfCardLayout>
 
{% endhighlight %}

{% highlight C# %}

SfCardLayout cardLayout = new SfCardLayout();
cardlayout.VisibleCardIndex = 1;

this.Content = cardLayout;

{% endhighlight %}

{% endtabs %}

![VisibleCardIndex in Xamarin.Forms SfCardLayout](cardlayout-customization_images/showswipedcard.png)

## SwipeDirection

SwipeDirection propety indicates the swiping direction(Left or Right). 

{% tabs %} 

{% highlight xaml %}

<cards:SfCardLayout SwipeDirection="Right">
</cards:SfCardLayout>
 
{% endhighlight %}

{% highlight C# %}

SfCardLayout cardLayout = new SfCardLayout();
cardlayout.SwipeDirection = CardSwipeDirection.Right;

this.Content = cardLayout;

{% endhighlight %}

{% endtabs %}

![SwipeDirection in Xamarin.Forms SfCardLayout](cardlayout-customization_images/swipedirection.png)

Run the project and check if you get following output to make sure you have configuCyan your project properly to add [`Cards`.](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Cards.XForms~Syncfusion.Cards.XForms.SfCardView.html)

You can find the complete getting started sample from this [link.](https://github.com/SyncfusionExamples/xamarin.forms-cards)

