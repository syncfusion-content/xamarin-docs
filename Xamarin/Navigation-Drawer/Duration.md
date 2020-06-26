---
layout: post
title: Duration in Syncfusion SfNavigationDrawer control for Xamarin.Forms
description: This section will explain about how to customize the duration of Xamarin.Forms NavigationDrawer control viewbox.
platform: Xamarin
control: SfNavigationDrawer
documentation: ug
---
# Animation duration in Xamarin NavigationDrawer (SfNavigationDrawer)

## Animation Duration in SfNavigationDrawer

The `Duration` property of SfNavigationDrawer indicates timeline for completing one animation cycle. Setting smaller duration value accelerates animation speed.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         DrawerWidth ="300"
                                         Duration="1"
                                         DrawerHeaderHeight="160">
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfNavigationDrawer navigationdrawer = new SfNavigationDrawer()
            {               
                DrawerWidth = 300,
                DrawerHeaderHeight = 160,
                Duration = 1f
            };

            this.Content = navigationdrawer;
        }
    }
}
    
{% endhighlight %}

{% endtabs %}

![Maximum Duration](Images/NavigatioDrawer_Duration_gif.gif)


