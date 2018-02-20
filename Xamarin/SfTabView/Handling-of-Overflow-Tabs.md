---
layout: post
title: Handling OverFlow Tabs
description: Handling of Overflow tabs in Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Handling overflow tabs

When having large number of tabs, by default scroller will be enabled to view the overflow of headers, in case needed, it can be selected from pop-up by setting `OverflowMode` of `SfTabView` as `DropDown`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView  OverflowMode="DropDown">
			
{% endhighlight %}

{% highlight C# %}

tabView.OverflowMode = OverflowMode.DropDown;
			
{% endhighlight %}

{% endtabs %}

By selection drop-down option for tab view control, there is a button named `“Overflow button”` (or `“More button”`) will be added to the header. When click on this button, it will display a pop-up to navigate the other indices.

N> Pop-up will display the text value only, it will show the title value of the respective tab item.

## How to customize the more button?

Appearance of the text can be customized through the APIs available `OverflowButtonSettings` of `SfTabView`. It has APIs to customize both text and font icons available in this button. 

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView.OverflowButtonSettings>
			<tabView:OverflowButtonSettings 
				BackgroundColor="Red" 
				DisplayMode="Text"
				Title="..."
				TitleFontSize="30"
				TitleFontColor="Yellow"/>
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
