---
layout: post
title: Sizing in Xamarin Busy Indicator Control | Syncfusion
description: Understand sizing options in the Syncfusion Xamarin Busy Indicator (SfBusyIndicator) control.
platform: Xamarin
control: SfBusyIndicator
documentation: ug
---

# Sizing in Xamarin Busy Indicator (SfBusyIndicator)

The size of the drawing area in the [`SfBusyIndicator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html) can be customized using the [`ViewBoxHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_ViewBoxHeight) and [`ViewBoxWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_ViewBoxWidth) properties, which allow you to set the height and width of the indicator.

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
                                       AnimationType="SlicedCircle" 
                                       ViewBoxWidth = "20" 
                                       ViewBoxHeight="20" 
                                       TextColor="Maroon"/>
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
                AnimationType = AnimationTypes.SlicedCircle,
                ViewBoxHeight = 20,
                ViewBoxWidth = 20,
                TextColor = Color.Maroon
            };

            this.Content = busyIndicator;
        }
    }
}
 
{% endhighlight %}

{% endtabs %}

![Height and width](images/heightand width.png)  
