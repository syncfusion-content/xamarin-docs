---
layout: post
title: IsBusy support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn how to enable and disable animation in SfBusyIndicator
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Make Busy Animation Idle

SfBusyIndicator control provides support to determine whether an animation needs to be executed or not. Setting the `IsBusy` property to false will stop the animation and removes the control from view.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
	x:Class="GettingStarted.BusyIndicatorPage">
<ContentPage.Content>
 <syncfusion:SfBusyIndicator x:Name="busyindicator" AnimationType="Ball" IsBusy="false" ViewBoxWidth = "150" ViewBoxHeight="150" TextColor="Maroon" />	
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

			SfBusyIndicator busyindicator = new SfBusyIndicator();
			busyindicator.AnimationType = AnimationTypes.Battery;
			busyindicator.ViewBoxWidth = 150;
			busyindicator.ViewBoxHeight = 150;
			busyindicator.IsBusy=false;
			busyindicator.TextColor = Color.Maroon;
			this.Content = busyindicator;
		}
	}
}
	
{% endhighlight %}

{% endtabs %}

N> The default value is true.


