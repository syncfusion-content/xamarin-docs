---
layout: post
title: Title support in Syncfusion SfBusyIndicator control for Xamarin.Forms
description: This section will explain how to add and customize title description on Xamarin.Forms SfBusyIndicator control.
platform: Xamarin
control: BusyIndicator
documentation: ug
---
# Set Header

## Set Header in Xamarin Busy Indicator  (SfBusyIndicator)

## Title

SfBusyIndicator provides option to set the text that indicates the information related to loading. This can be done using `Title` property.

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
                                       Title="Loading..."
                                       ViewBoxHeight="150"/>
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
                Title = "Loading..."
            };

            this.Content = busyIndicator;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## TextColor

SfBusyIndicator provides options to change the color of the text. The color of the text can be changed using the [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_TextColorProperty) property.

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
                                       Title="Loading..."
                                       ViewBoxHeight="150" 
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
                AnimationType = AnimationTypes.Ball,
                ViewBoxHeight = 150,
                ViewBoxWidth = 150,
                TextColor = Color.Maroon,
                Title = "Loading..."
            };

            this.Content = busyIndicator;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## TextSize

SfBusyIndicator provides options to change the size of the text. The size of the text can be changed using the [`TextSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_TextSizeProperty) property.

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
                                       Title="Loading..."
                                       TextSize="10"
                                       ViewBoxHeight="150" 
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
                AnimationType = AnimationTypes.Ball,
                ViewBoxHeight = 150,
                ViewBoxWidth = 150,
                TextColor = Color.Maroon,
                Title = "Loading...",
                TextSize = 10
            };

            this.Content = busyIndicator;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## TitlePlacement

SfBusyIndicator provides options to set the `Title` at the top or bottom of the Busy Indicator. The `Title` can be set using the [`TitlePlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfBusyIndicator.XForms.SfBusyIndicator.html#Syncfusion_SfBusyIndicator_XForms_SfBusyIndicator_TitlePlacementProperty) property. When the `Title` is not needed, set the `TitlePlacement` property of SfBusyIndicator to None.

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
                                       ViewBoxWidth = "150" 
                                       Title="Loading..."
                                       TitlePlacement="None"
                                       ViewBoxHeight="150" 
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
                AnimationType = AnimationTypes.Ball,
                ViewBoxHeight = 150,
                ViewBoxWidth = 150,
                TextColor = Color.Maroon,
                Title = "Loading...",
                TitlePlacement= TitlePlacement.None
            };

            this.Content = busyIndicator;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Title](images/Title.png) 
