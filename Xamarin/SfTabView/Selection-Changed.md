---
layout: post
title: Selection Changed
description: Selection changed event in TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Selection Changed

When selection changed due to swiping or by dynamically setting the `SelectedIndex` property of `SfTabView`, there is an event available in tab view control to get notified for the change.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView  SelectionChanged="SfTabView_SelectionChanged" >

{% endhighlight %}

{% highlight C# %}

tabView.SelectionChanged += SfTabView_SelectionChanged;

		// Raised when selected index changed
	private void SfTabView_SelectionChanged(object sender, SelectionChangedEventArgs e)
	{
		var selectedIndex = e.Index;
	}

{% endhighlight %}

{% endtabs %}

## Enable Swiping

When selection changed is needs to be restricted through user interaction, `EnableSwiping` property of `SfTabView` can be set as `false`.