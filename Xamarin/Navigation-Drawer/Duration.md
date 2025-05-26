---
layout: post
title: Animation Duration in Xamarin Navigation Drawer Control | Syncfusion
description: Explore the animation duration feature in the Syncfusion Xamarin Navigation Drawer (SfNavigationDrawer) control.
platform: Xamarin
control: SfNavigationDrawer
documentation: ug
---
# Animation Duration in Xamarin Navigation Drawer (SfNavigationDrawer)

## Animation Duration in SfNavigationDrawer

The [`Duration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_Duration) property of the [`SfNavigationDrawer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html) specifies the timeline for completing one animation cycle. Setting a smaller duration value increases the animation speed.

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


