---
layout: post
title: Accessibility in Xamarin Cards control | Syncfusion
description: Learn about Accessibility support in Syncfusion Essential Studio® Xamarin Cards control, its elements and more.
platform: xamarin
control: SfCardLayout
documentation : ug
---

# Accessibility in Xamarin Cards

The [`SfCardLayout`](https://help.syncfusion.com/xamarin/cards/getting-started#sfcardlayout) control has built-in automation Id for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the [`SfCardLayout`](https://help.syncfusion.com/xamarin/cards/getting-started#sfcardlayout) control. To keep unique AutomationId, these inner elements’ AutomationIds are updated based on the control’s `AutomationId`.

For example, if you set SfCardLayouts' AutomationId as "CardLayout" and also enable the accessibility option in mobile device to read text, then the automation framework will interact with [`SfCardLayout`](https://help.syncfusion.com/xamarin/cards/getting-started#sfcardlayout) inner elements and voice over the text like "CardLayout SfCardLayoutItem 2 of 3" (2 denotes the current item and 3 denotes the total count) when you swipe the card.

N> Accessibility support works on Android and iOS platform only.

{% tabs %}

{% highlight xaml %}

<cards:SfCardLayout SwipeDirection="Left" HeightRequest="500" BackgroundColor="#F0F0F0">

	<cards:SfCardView>
		<Label  Text="Cyan" BackgroundColor="Cyan"/>
	</cards:SfCardView>

	<cards:SfCardView>
		<Label  Text="Yellow" BackgroundColor="Yellow"/>
	</cards:SfCardView>

	<cards:SfCardView>
		<Label  Text="Orange" BackgroundColor="Orange"/>
	</cards:SfCardView>  

</cards:SfCardLayout>

{% endhighlight %}

{% highlight c# %}

SfCardLayout cardLayout = new SfCardLayout();

//Add children for card layout 
cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Cyan", BackgroundColor=Color.Cyan }});

cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Yellow", BackgroundColor=Color.Yellow }});

cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Orange", BackgroundColor=Color.Orange }});

this.Content = cardLayout;

{% endhighlight %}

{% endtabs %} 

![Initializing Xamarin.Forms SfCardLayout](getting-started_images/layout.gif)
