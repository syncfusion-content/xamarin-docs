---
layout: post
title: Duration support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to customize the duration of the control viewbox
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Duration

The `Duration` property for the SfBusyIndicator allows the user to control the speed of the animation.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
	x:Class="GettingStarted.BusyIndicatorPage">
<ContentPage.Content>
 <syncfusion:SfBusyIndicator x:Name="busyindicator" AnimationType="SlicedCircle"  ViewBoxWidth = "20" ViewBoxHeight="20" Duration="50" TextColor="Maroon" />	
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
			busyIndicator.Duration = 50;
			busyIndicator.TextColor = Color.Maroon;
			this.Content = busyIndicator;
		}
	}
}
    
{% endhighlight %}

{% endtabs %}

![](images/heightand width.png)  



