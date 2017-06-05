---
layout: post
title: Swipe gesture in Syncfusion's NavigationDrawer control for Xamarin.Forms
description: Learn how to open Drawer panel using swipe gesture.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# Swipe Gesture and Sensitivity

NavigationDrawer supports swipe gesture for opening and closing the drawer. 

## Enabling Swipe Gesture

It can be enabled/disabled using `EnableSwipeGesture` property.

{% tabs %}

{% highlight xaml %}

	<navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" EnableSwipeGesture="True">
		<navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
			<Grid BackgroundColor="#1aa1d6" VerticalOptions="Center" HorizontalOptions="Center">
				<Label Text="Header view" FontSize="16" VerticalOptions="Center" HorizontalOptions="Center"/>
			</Grid>
		</navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
	</navigationdrawer:SfNavigationDrawer>

{% endhighlight %}	
	
{% highlight c# %} 

navigationDrawer.EnableSwipeGesture = true;

{% endhighlight %}

{% endtabs %}

## Swipe Sensitivity

In smaller screens user may find it difficult to swipe the drawer from the edge in such cases we can increase the swipe region using `TouchThreshold` property. It can be set as below:

{% tabs %}

{% highlight xaml %}

	<navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" EnableSwipeGesture="True" TouchThreshold="70">
		<navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
			<Grid BackgroundColor="#1aa1d6" VerticalOptions="Center" HorizontalOptions="Center">
				<Label Text="Header view" FontSize="16" VerticalOptions="Center" HorizontalOptions="Center"/>
			</Grid>
		</navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
	</navigationdrawer:SfNavigationDrawer>

{% endhighlight %}	
	
{% highlight c# %} 

navigationDrawer.TouchThreshold = 70;

{% endhighlight %}

{% endtabs %}