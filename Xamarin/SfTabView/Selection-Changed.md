---
layout: post
title: Selection Changed
description: Selection changed event in TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Selection Changed

The `SelectionChanged` event is used to notify when the selection is changed by swiping or dynamically setting the `SelectedIndex` property of `SfTabView`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView  SelectionChanged="SfTabView_SelectionChanged" >

{% endhighlight %}

{% highlight C# %}

tabView.SelectionChanged += SfTabView_SelectionChanged;

// Occurred when the selected index is changed

private void SfTabView_SelectionChanged(object sender, SelectionChangedEventArgs e)
{
	var selectedIndex = e.Index;
}

{% endhighlight %}

{% endtabs %}

## Enable swiping

When the selection changed event is needs to be restricted through user interaction, the `EnableSwiping` property of `SfTabView` can be set to `false`.