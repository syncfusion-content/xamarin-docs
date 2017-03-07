---
layout: post
title: AnimationTypes in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: Learn various animation types available in SfBusyIndicator
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Animation Type

The `AnimationType` property for the SfBusyIndicator allows the user to set one of the 15 animations from the built-in animations.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
	x:Class="GettingStarted.BusyIndicatorPage">
<ContentPage.Content>
 <syncfusion:SfBusyIndicator x:Name="busyindicator" AnimationType="Ball" Title="Loading..." BackgroundColor="Blue" TextColor="White" />	
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
			busyindicator.AnimationType = AnimationTypes.Ball;
			busyindicator.BackgroundColor = Color.Blue;
			busyindicator.TextColor = Color.White;
			busyindicator.Title ="Loading…";
			this.Content = busyindicator;
		}
	}
}
	
{% endhighlight %}

{% endtabs %}

![](images/ball1.png)

Busy Indicator with Ball type animation 
{:.caption}

![](images/HorizontalPulsingBox.png) 

Busy Indicator with HorizontalPulsingBox type animation 
{:.caption}

![](images/rectangle.png) 

Busy Indicator with Rectangle type animation 
{:.caption}
 
![](images/battery.png) 

Busy Indicator with Battery type animation 
{:.caption}
 
![](images/globe.png) 

Busy Indicator with Globe type animation 
{:.caption}
 
![](images/singlecircle.png) 

Busy Indicator with SingleCircle type animation 
{:.caption}

![](images/SlicedCircle.png) 

Busy Indicator with SlicedCircle type animation 
{:.caption}
 
![](images/doublecircle.png) 

Busy Indicator with DoubleCircle type animation 
{:.caption}
 
![](images/ecg.png) 

Busy Indicator with ECG type animation 
{:.caption}
 
![](images/print.png) 

Busy Indicator with Print type animation 
{:.caption}

![](images/box.png) 

Busy Indicator with Box type animation 
{:.caption}

![](images/gear.png) 

Busy Indicator with Gear type animation 
{:.caption}

![](images/timer.png) 

Busy Indicator with MovieTimer type animation 
{:.caption}

![](images/zoomingtarget.png) 

Busy Indicator with ZoomingTarget type animation 
{:.caption}

![](images/rollingball.png) 

Busy Indicator with RollingBall type animation 
{:.caption}





 
