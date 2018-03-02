---
layout: post
title: Handling OverFlow Tabs
description: Handling of Overflow tabs in Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Handling overflow tabs

When you have large number of tabs, by default, the scroller will be enabled to view the overflow of headers, if needed. It can be selected from the pop-up by setting the `OverflowMode` property of `SfTabView` to `DropDown`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView  OverflowMode="DropDown">
			
{% endhighlight %}

{% highlight C# %}

tabView.OverflowMode = OverflowMode.DropDown;
			
{% endhighlight %}

{% endtabs %}

By selecting the drop-down option for tab view control, The `“Overflow button”` (or `“More button”`) will be added to the header. When you click this button, a pop-up will be displayed to navigate the other indices.

N> The pop-up will display the text value and title value of the respective tab item.

## How to customize the more button?

Appearance of the text can be customized through the APIs that are available on the `OverflowButtonSettings` property of `SfTabView`. This property has APIs to customize the both text and font icons available in the more button. 

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView.OverflowButtonSettings>
	<tabView:OverflowButtonSettings 
	BackgroundColor="Red" 
	DisplayMode="Text"
	Title="..."
	TitleFontSize="30"
	TitleFontColor="Yellow"
	/>
</tabView:SfTabView.OverflowButtonSettings>	

{% endhighlight %}

{% highlight C# %}

var overflowButtonSettings = new OverflowButtonSettings();
overflowButtonSettings.BackgroundColor = Color.Red;
overflowButtonSettings.DisplayMode = OverflowButtonDisplayMode.Text;
overflowButtonSettings.Title = "...";
overflowButtonSettings.TitleFontSize = 30;
overflowButtonSettings.TitleFontColor = Color.Yellow;
tabView.OverflowButtonSettings = overflowButtonSettings;
			
{% endhighlight %}

{% endtabs %}
