---
layout: post
title: Animation Duration in Xamarin Busy Indicator Control | Syncfusion
description: Discover the animation duration support in Syncfusion Xamarin Busy Indicator (SfBusyIndicator) control.
platform: Xamarin
control: SfBusyIndicator
documentation: ug
---

# Animation Duration in Xamarin Busy Indicator (SfBusyIndicator)

The [`Duration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_Duration) property of the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) specifies the time taken to complete one animation cycle. A smaller duration value results in faster animation speed.

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
                                       AnimationType="Battery" 
                                       ViewBoxHeight="100"
                                       ViewBoxWidth="100"
                                       Duration="0.5"/>
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
                AnimationType = AnimationTypes.Battery,
                ViewBoxWidth = 100,
                ViewBoxHeight = 100,
                Duration = 0.5f
            };

            this.Content = busyIndicator;
        }
    }
}
    
{% endhighlight %}

{% endtabs %}

![Maximum Duration](hostingsfbusyindicator_images/Maximum.gif)




