---
layout: post
title: Selection Indicator 
description: Selection Indicator in Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Selection Indicator strip

Selection indicator strip can be used to indicate the selected index of the tab view control. It can be customized with the built in APIs available in `SelectionIndicatorSettings` of `SfTabView`.

![](images/Selection-Indicator/tabstyle02.png)


Selection indicator can be positioned below the title or above the title or else it can be filled in the entire selected header space.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView.SelectionIndicatorSettings>
			<tabView:SelectionIndicatorSettings
				Color="Yellow" 
				Position="Top" 
				StrokeThickness="10"/>
		</tabView:SfTabView.SelectionIndicatorSettings>
			
{% endhighlight %}

{% highlight C# %}

		var selectionIndicatorSettings = new SelectionIndicatorSettings();
		selectionIndicatorSettings.Color = Color.Yellow;
		selectionIndicatorSettings.Position = SelectionIndicatorPosition.Top;
		selectionIndicatorSettings.StrokeThickness = 10;

		tabView.SelectionIndicatorSettings = selectionIndicatorSettings;

			
{% endhighlight %}

{% endtabs %}

N> Stroke thickness is not applicable when selection indicator’s position is set as Fill.

