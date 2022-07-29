---
layout: post
title: Setting Toggle Animations in Xamarin Navigation Drawer | Syncfusion
description: Learn here all about Setting Toggle Animations support in Syncfusion Xamarin Navigation Drawer (SfNavigationDrawer) control and more.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# Setting Toggle Animations in Xamarin Navigation Drawer

The drawer toggling animation can be changed using [`Transition`] property and it can be set to three different values. They are

* [`SlideOnTop`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.Transition.html#Syncfusion_SfNavigationDrawer_XForms_Transition_SlideOnTop)

* [`Push`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.Transition.html#Syncfusion_SfNavigationDrawer_XForms_Transition_Push)

* [`Reveal`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.Transition.html#Syncfusion_SfNavigationDrawer_XForms_Transition_Reveal)

N> The default animation is [`SlideOnTop`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.Transition.html#Syncfusion_SfNavigationDrawer_XForms_Transition_SlideOnTop).

## SlideOnTop

The navigation pane overlays the main content area when opened. It can be set as shown below:

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         Transition="SlideOnTop" 
                                         DrawerHeaderHeight="50">
        <navigationdrawer:SfNavigationDrawer.ContentView>
            <StackLayout>
                <Grid HeightRequest="50" 
                      VerticalOptions="Start" 
                      BackgroundColor="#1aa1d6">
                    <Button x:Name="hamburgerButton" 
                            HeightRequest="50" 
                            WidthRequest="50" 
                            HorizontalOptions="Start" 
                            FontSize="20" 
                            BackgroundColor="#1aa1d6" 
                            Clicked="hamburgerButton_Clicked"/>
                </Grid>
            </StackLayout>
        </navigationdrawer:SfNavigationDrawer.ContentView>
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Grid BackgroundColor="#1aa1d6" 
                  VerticalOptions="Center" 
                  HorizontalOptions="Center">
                <Label Text="Header view" 
                       FontSize="16" 
                       VerticalOptions="Center" 
                       HorizontalOptions="Center"/>
            </Grid>
        </navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
    </navigationdrawer:SfNavigationDrawer>
</ContentPage>
	
{% endhighlight %}	
	
{% highlight c# %} 

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            navigationDrawer.DrawerHeight = 200; 
            navigationDrawer.Transition = Syncfusion.SfNavigationDrawer.XForms.Transition.SlideOnTop;
            hamburgerButton.Image = (FileImageSource)ImageSource.FromFile("hamburger_icon.png");

        }

        void hamburgerButton_Clicked(object sender, EventArgs e)
        {
            navigationDrawer.ToggleDrawer();
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SlideOnTop](Images/SlideOnTop.png)

## Push

The navigation pane is hidden. It pushes the main content area in opposite side up to [`drawer width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_DrawerWidth) when opened. It can be set as shown below:

{% tabs %}	

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         Transition="Push" 
                                         DrawerHeaderHeight="50">
        <navigationdrawer:SfNavigationDrawer.ContentView>
            <StackLayout>
                <Grid HeightRequest="50" 
                      VerticalOptions="Start" 
                      BackgroundColor="#1aa1d6">
                    <Button x:Name="hamburgerButton" 
                            HeightRequest="50" 
                            WidthRequest="50" 
                            HorizontalOptions="Start" 
                            FontSize="20" 
                            BackgroundColor="#1aa1d6" 
                            Clicked="hamburgerButton_Clicked"/>
                </Grid>
            </StackLayout>
        </navigationdrawer:SfNavigationDrawer.ContentView>
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Grid BackgroundColor="#1aa1d6" 
                  VerticalOptions="Center" 
                  HorizontalOptions="Center">
                <Label Text="Header view" 
                       FontSize="16" 
                       VerticalOptions="Center" 
                       HorizontalOptions="Center"/>
            </Grid>
        </navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
    </navigationdrawer:SfNavigationDrawer>
</ContentPage>

{% endhighlight %}
	
{% highlight c# %} 

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            navigationDrawer.DrawerHeight = 200;
            navigationDrawer.Transition = Syncfusion.SfNavigationDrawer.XForms.Transition.Push;
            hamburgerButton.Image = (FileImageSource)ImageSource.FromFile("hamburger_icon.png");

        }

        void hamburgerButton_Clicked(object sender, EventArgs e)
        {
            navigationDrawer.ToggleDrawer();
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Push](Images/Push.png)

## Reveal

The navigation pane is hidden behind the main content. Main content moves away in opposite side up to [`drawer width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_DrawerWidth) to show the drawer content. It can be set as shown below:

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         Transition="Reveal" 
                                         DrawerHeaderHeight="50">
        <navigationdrawer:SfNavigationDrawer.ContentView>
            <StackLayout>
                <Grid HeightRequest="50" 
                      VerticalOptions="Start" 
                      BackgroundColor="#1aa1d6">
                    <Button x:Name="hamburgerButton" 
                            HeightRequest="50" 
                            WidthRequest="50" 
                            HorizontalOptions="Start" 
                            FontSize="20" 
                            BackgroundColor="#1aa1d6" 
                            Clicked="hamburgerButton_Clicked"/>
                </Grid>
            </StackLayout>
        </navigationdrawer:SfNavigationDrawer.ContentView>
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Grid BackgroundColor="#1aa1d6" 
                  VerticalOptions="Center" 
                  HorizontalOptions="Center">
                <Label Text="Header view" 
                       FontSize="16" 
                       VerticalOptions="Center" 
                       HorizontalOptions="Center"/>
            </Grid>
        </navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
    </navigationdrawer:SfNavigationDrawer>
</ContentPage>
	
{% endhighlight %}	
	
{% highlight c# %} 

using System;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            navigationDrawer.DrawerHeight = 200;
            navigationDrawer.Transition = Syncfusion.SfNavigationDrawer.XForms.Transition.Reveal;
            hamburgerButton.Image = (FileImageSource)ImageSource.FromFile("hamburger_icon.png");

        }

        void hamburgerButton_Clicked(object sender, EventArgs e)
        {
            navigationDrawer.ToggleDrawer();
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Reveal](Images/Reveal.png)
