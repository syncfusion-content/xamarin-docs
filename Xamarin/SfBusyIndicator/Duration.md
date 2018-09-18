---
layout: post
title: Duration support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to customize the duration of the control viewbox
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Animation Speed

The `Duration` property of SfBusyIndicator indicates the timeline for completing one animation cycle. Setting smaller duration value accelerates the animation speed.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
	x:Class="GettingStarted.BusyIndicatorPage">
<ContentPage.Content>
 <syncfusion:SfBusyIndicator x:Name="busyindicator" AnimationType="SlicedCircle"  ViewBoxWidth = "20" ViewBoxHeight="20" Duration="25" TextColor="Maroon" />	
</ContentPage.Content>
</ContentPage>
	
{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfBusyIndicator.XForms;
using Xamarin.Forms;
namespace GettingStarted
{
	public partial class BusyIndicatorPage : ContentPage
	{
		public BusyIndicatorPage()
		{
			InitializeComponent();

			SfBusyIndicator busyIndicator = new SfBusyIndicator();
			busyIndicator.AnimationType = AnimationTypes.SlicedCircle;
			busyIndicator.ViewBoxWidth = 20;
			busyIndicator.ViewBoxHeight = 20;
			busyIndicator.Duration = 25;
			busyIndicator.TextColor = Color.Maroon;
			this.Content = busyIndicator;
		}
	}
}
    
{% endhighlight %}

{% endtabs %}

N> `Android`
Minimum animation speed is [`0.1`] and Maximum animation speed is [`25`]. The default speed is [`1`].

`UWP`
Minimum animation speed is [`10`] and Maximum animation speed is [`500`]. The default speed is [`115`].


![](hostingsfbusyindicator_images/Maximum.gif)




![](hostingsfbusyindicator_images/Minimum.gif)




