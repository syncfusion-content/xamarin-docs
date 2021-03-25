---
layout: post
title: Automation ID in Syncfusion SfCardLayout control in Xamarin.Forms
description: Learn how to use the automation ID in SfCardLayout control for running the test cases in Xamarin.Forms
platform: xamarin
control: SfCardLayout
documentation : ug
---

# AutomationId in SfCardLayout

The SfCardLayout control has built-in automation Id for inner elements. The `AutomationId` API allows the automation framework to find and interact with the inner elements of the `SfCardLayout` control. To keep unique AutomationId, these inner elements’ AutomationIds are updated based on the control’s `AutomationId`.

For example, if you set SfCardLayout’s AutomationId as "CardLayout" and enable the accessibility option in mobile device to read text, then the automation framework will interact with [SfCardLayout`](https://help.syncfusion.com/xamarin/cards/getting-started#sfcardlayout) inner elements and voice over the text like "CardLayout SfCardLayoutItem 2 of 3" (2 denotes the current item and 3 denotes the total count) when you swipe the card.

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

{% highlight C# %} 

SfCardLayout cardLayout = new SfCardLayout();

//Add children for card layout 
cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Cyan", BackgroundColor=Color.Cyan }});

cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Yellow", BackgroundColor=Color.Yellow }});

cardLayout.Children.Add(new SfCardView(){Content = new Label(){ Text="Orange", BackgroundColor=Color.Orange }});

this.Content = cardLayout;

{% endhighlight %}

{% endtabs %} 

![Initializing Xamarin.Forms SfCardLayout](getting-started_images/layout.gif)
