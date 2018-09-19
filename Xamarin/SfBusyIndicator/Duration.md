---
layout: post
title: Duration support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to customize the duration of the control viewbox
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Animation duration

The `Duration` property of SfBusyIndicator indicates timeline for completing one animation cycle. Setting smaller duration value accelerates animation speed.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
	x:Class="GettingStarted.BusyIndicatorPage">
<ContentPage.Content>
 <syncfusion:SfBusyIndicator x:Name="busyindicator" AnimationType="Battery"  ViewBoxWidth = "100" ViewBoxHeight="100" Duration="0.5" />	
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
			busyIndicator.ViewBoxWidth = 100;
			busyIndicator.ViewBoxHeight = 100;
			busyIndicator.Duration = 0.5;
			this.Content = busyIndicator;
		}
	}
}
    
{% endhighlight %}

{% endtabs %}

![](hostingsfbusyindicator_images/Maximum.gif)




