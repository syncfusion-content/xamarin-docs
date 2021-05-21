---
layout: post
title: Sizing in Xamarin Busy Indicator control | Syncfusion
description: Learn here all about Sizing support in Syncfusion Xamarin Busy Indicator (SfBusyIndicator) control and more.
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Sizing in Xamarin Busy Indicator (SfBusyIndicator)

## Sizing in Xamarin BusyIndicator (SfBusyIndicator)

Drawing size can be customized in SfBusyIndicator. `ViewBoxHeight` and `ViewBoxWidth` properties can be used to set height and width of the Indicator.

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
