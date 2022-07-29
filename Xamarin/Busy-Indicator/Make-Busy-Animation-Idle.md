---
layout: post
title: Make Busy Animation Idle in Xamarin Busy Indicator | Syncfusion
description: Learn here all about Make Busy Animation Idle support in Syncfusion Xamarin Busy Indicator (SfBusyIndicator) control and more.
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Make Busy Animation Idle in Xamarin Busy Indicator (SfBusyIndicator)

## Make Busy Animation Idle in Xamarin BusyIndicator(SfBusyIndicator)

[`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) control provides support to determine whether an animation needs to be executed or not. Setting the [`IsBusy`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_IsBusy) property to false will stop the animation and removes the control from view.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:busyindicator="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <busyindicator:SfBusyIndicator x:Name="busyindicator" 
                                       AnimationType="Ball" 
                                       ViewBoxWidth = "150" 
                                       ViewBoxHeight="150" 
                                       TextColor="Maroon" 
                                       IsBusy="False"/>
    </ContentPage.Content>
</ContentPage>
	
{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfBusyIndicator.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfBusyIndicator busyIndicator = new SfBusyIndicator()
            {
                AnimationType = AnimationTypes.Ball,
                ViewBoxHeight = 150,
                ViewBoxWidth = 150,
                TextColor = Color.Maroon,
                IsBusy = false
            };

            this.Content = busyIndicator;
        }
    }
}
	
{% endhighlight %}

{% endtabs %}

N> The default value is true.


