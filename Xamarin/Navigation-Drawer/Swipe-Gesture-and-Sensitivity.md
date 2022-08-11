---
layout: post
title: SwipGesture and Sensitivity in Xamarin Navigation Drawer | Syncfusion
description: Learn here all about SwipGesture and its Sensitivity support in Syncfusion Xamarin Navigation Drawer (SfNavigationDrawer) control and more.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# SwipeGesture and its Sensitivity in Xamarin Navigation Drawer

NavigationDrawer supports swipe gesture for opening and closing the drawer. 

## Enabling Swipe Gesture

It can be enabled/disabled using [`EnableSwipeGesture`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_EnableSwipeGesture) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         EnableSwipeGesture="True">
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

navigationDrawer.EnableSwipeGesture = true;

{% endhighlight %}

{% endtabs %}

## Swipe Sensitivity

In smaller screens user may find it difficult to swipe the drawer from the edge in such cases we can increase the swipe region using [`TouchThreshold`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_TouchThreshold) property. It can be set as below:

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         EnableSwipeGesture="True"
                                         TouchThreshold="70">
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

navigationDrawer.TouchThreshold = 70;

{% endhighlight %}

{% endtabs %}
