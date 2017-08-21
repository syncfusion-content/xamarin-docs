---
layout: post
title: Placing and Dragging Syncfusion RadialMenu control in Xamarin.Forms
description: Postioning and Dragging RadialMenu control in Xamarin.Forms
platform: Xamarin
control: SfRadialMenu
documentation: ug
---

# Placing and Dragging RadialMenu

We can place SfRadialMenu anywhere on its parent layout and  able to drag it with in the parent layout. 

## Dragging RadialMenu

We can Enable/Disable dragging by using the property `IsDragEnabled`.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="UTF-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" BackgroundColor="White"
 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="RadialMenuGettingStarted.RadialMenuPage"
 xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms">
    
<ContentPage.Content>
		<radialMenu:SfRadialMenu x:Name="radialMenu" IsDragEnabled="true" CenterButtonText=""  CenterButtonBackText="" CenterButtonFontFamily="Segoe MDL2 Assets.ttf" CenterButtonBackFontFamily="Segoe MDL2 Assets.ttf" CenterButtonRadius="30" RimColor="#FFCDCBCE" RimRadius="100" CenterButtonFontSize="26" CenterButtonTextColor="White"
			CenterButtonBackgroundColor="#FF898889" CenterButtonBorderColor="White" CenterButtonBorderThickness="3">
		</radialMenu:SfRadialMenu>
	</ContentPage.Content>
</ContentPage> 

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.SfRadialMenu;
using Xamarin.Forms;

public class App : Application
    {
        public App()
        {
            MainPage = new RadialMenuPage ();
        }

    }
Public class RadialMenuPage : ContentPage
{
   
	public RadialMenuPage ()
	{
		InitializeComponent();
		//Creating instance for RadialMenu
		SfRadialMenu radialMenu = new SfRadialMenu();

		//Initilizing RadialMenu's properties
		radialMenu.CenterButtonText = "\uE713";
		radialMenu.CenterButtonFontFamily = "Segoe MDL2 Assets.ttf";
		radialMenu.CenterButtonBackFontFamily = "Segoe MDL2 Assets.ttf";
		radialMenu.CenterButtonRadius = 32;
		radialMenu.CenterButtonBorderColor = Color.White;
		radialMenu.IsDragEnabled = true;

		this.Content = radialMenu;
	}
}
{% endhighlight %}
{% endtabs %}
![](images/dragging.png)

## Placing RadialMenu

We can able to place RadialMenu anywhere on its parent layout. RadialMenu's position is calculated based on parent layout's center point.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="UTF-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" BackgroundColor="White"
 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="RadialMenuGettingStarted.RadialMenuPage"
 xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms">
    
<ContentPage.Content>
		<radialMenu:SfRadialMenu x:Name="radialMenu" IsDragEnabled="true" CenterButtonText="" Point="140,250" CenterButtonBackText="" CenterButtonFontFamily="Segoe MDL2 Assets.ttf" CenterButtonBackFontFamily="Segoe MDL2 Assets.ttf" CenterButtonRadius="30" RimColor="#FFCDCBCE" RimRadius="100" CenterButtonFontSize="26" CenterButtonTextColor="White"
			CenterButtonBackgroundColor="#FF898889" CenterButtonBorderColor="White" CenterButtonBorderThickness="3">
		</radialMenu:SfRadialMenu>
	</ContentPage.Content>
</ContentPage> 

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.SfRadialMenu;
using Xamarin.Forms;

public class App : Application
    {
        public App()
        {
            MainPage = new RadialMenuPage ();
        }

    }
Public class RadialMenuPage : ContentPage
{
   
	public RadialMenuPage ()
	{
		InitializeComponent();
		//Creating instance for RadialMenu
		SfRadialMenu radialMenu = new SfRadialMenu();

		//Initilizing RadialMenu's properties
		radialMenu.CenterButtonText = "\uE713";
		radialMenu.CenterButtonFontFamily = "Segoe MDL2 Assets.ttf";
		radialMenu.CenterButtonBackFontFamily = "Segoe MDL2 Assets.ttf";
		radialMenu.CenterButtonRadius = 32;
		radialMenu.CenterButtonBorderColor = Color.White;
		radialMenu.IsDragEnabled = true;
        radialMenu.Point = new Point(140, 250);

		this.Content = radialMenu;
	}
}
{% endhighlight %}
{% endtabs %}

![](images/position.png)