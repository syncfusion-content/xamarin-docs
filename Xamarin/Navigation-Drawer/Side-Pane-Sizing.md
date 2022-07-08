---
layout: post
title: Setting Sliding Panel size in Xamarin Navigation Drawer | Syncfusion
description: Learn here all about Setting Sliding Panel size support in Syncfusion Xamarin Navigation Drawer (SfNavigationDrawer) control and more.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# Setting Sliding Panel size in Xamarin Navigation Drawer

The size of side pane can be adjusted using [`DrawerHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_DrawerHeight) and [`DrawerWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_DrawerWidth) properties.

## Drawer Height

[`DrawerHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_DrawerHeight) property is used to change the height of side pane when the Position is Top or Bottom.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         DrawerHeight="40" 
                                         Position="Top">       
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Label Text="This is a very short content used to demonstrate the DrawerHeight property "/>            
        </navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
    </navigationdrawer:SfNavigationDrawer>
</ContentPage>
	
{% endhighlight %}	
	
{% highlight c# %} 


Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer navigationDrawer = new Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer();

navigationDrawer.Position = Position.Top;

navigationDrawer.DrawerHeight = 40;

navigationDrawer.DrawerHeaderView = new Label()

{

    Text = "This is a very short content used to demonstrate the DrawerHeight property"

};

Content = navigationDrawer;

{% endhighlight %}

{% endtabs %}

![Drawer height](Images/DrawerHeight.png)

## Drawer Width

[`DrawerWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_DrawerWidth) property is used to change the width of side pane when the Position is Left or Right.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         DrawerWidth="200" 
                                         Position="Left">       
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Label Text="This is a very short content used to demonstrate the DrawerHeight property "/>            
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
            SfNavigationDrawer navigationDrawer = new SfNavigationDrawer()
            {
                Position = Position.Left,
                DrawerWidth = 200,
                DrawerHeaderView = new Label()
                {
                    Text = "This is a very short content used to demonstrate the DrawerHeight property"
                }
            };

            Content = navigationDrawer;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Drawer width](Images/DrawerWidth.png)
