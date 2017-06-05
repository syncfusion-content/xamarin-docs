---
layout: post
title: Toggling drawer in Syncfusion NavigationDrawer control for Xamarin.Forms
description: Learn how to toggle the DrawerView panel.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# Toggling Drawer

Drawer can be toggled using

*	IsOpen property

*	ToggleDrawer method

*	Swipe gesture

## Opening Drawer Programmatically
`IsOpen` property and ToggleDrawer method can be used to open or close the drawer programmatically.

{% tabs %}

{% highlight xaml %}

	<navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" IsOpen="True">
		<navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
			<Grid BackgroundColor="#1aa1d6" VerticalOptions="Center" HorizontalOptions="Center">
				<Label Text="Header view" FontSize="16" VerticalOptions="Center" HorizontalOptions="Center"/>
			</Grid>
		</navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
	</navigationdrawer:SfNavigationDrawer>

{% endhighlight %}	
	
{% highlight c# %} 

navigationDrawer.IsOpen = true;

{% endhighlight %}

{% endtabs %}

Using `ToggleDrawer` method,

{% highlight c# %} 

navigationDrawer.ToggleDrawer();

{% endhighlight %}

Toggling drawer through swipe gesture is explained in `Swipe Gesture and Sensitivity` section.