---
layout : post
title : Data Binding  in Syncfusion RadialMenu control for Xamarin.Forms
description : Learn how to perform DataBinding in RadialMenu
platform : xamarin
control : SfRadialMenu
documentation : ug
---

# Populating Items

This section explains about the ways of populating items through SfRadailMenuItem and Item source with Item Template.

## Through RadialMenuItems

By passing collection of `SfRadialMenuItem` we can get the view of `SfRadialMenu` control. And SfRadialMenuItem class provides various options to customize the items by giving Custom views, Font Icons and Images. And it is possible to add RadialMenu items hierarchically. Item selection can be identified by using ItemTapped event. The ItemTapped event will be fired whenever we tap an item from RadialMenu.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="UTF-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" BackgroundColor="White"
 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="RadialMenuGettingStarted.RadialMenuPage"
 xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms">
    
<ContentPage.Content>
           <radialMenu:SfRadialMenu x:Name="radial_Menu" CenterButtonText="\uE713" CenterButtonBackText="\uE72B" CenterButtonFontFamily="Segoe MDL2 Assets.ttf" CenterButtonRadius="32">
				<radialMenu:SfRadialMenu.Items>
					<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uE701" IconFontFamily="Segoe MDL2 Assets.ttf">
						<radialMenu:SfRadialMenuItem.Items>
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEC3B" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem  ItemTapped="Handle_ItemTapped" FontIconText="\uEC3A" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEC39" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEC38" IconFontFamily="Segoe MDL2 Assets.ttf" />
						</radialMenu:SfRadialMenuItem.Items>
					</radialMenu:SfRadialMenuItem>
					<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uE702" IconFontFamily="Segoe MDL2 Assets.ttf">
						<radialMenu:SfRadialMenuItem.Items>
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEC3B" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEC3A" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEC39" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEC38" IconFontFamily="Segoe MDL2 Assets.ttf" />
						</radialMenu:SfRadialMenuItem.Items>
					</radialMenu:SfRadialMenuItem>
					<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEA8F" IconFontFamily="Segoe MDL2 Assets.ttf">
						<radialMenu:SfRadialMenuItem.Items>
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uE7ED" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uE877" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEA8F" IconFontFamily="Segoe MDL2 Assets.ttf" />
						</radialMenu:SfRadialMenuItem.Items>
					</radialMenu:SfRadialMenuItem>
					<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uE706" IconFontFamily="Segoe MDL2 Assets.ttf">
						<radialMenu:SfRadialMenuItem.Items>
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" IconFontSize="16" FontIconText="\uEC8A" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" IconFontSize="18" FontIconText="\uEC8A" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" IconFontSize="20" FontIconText="\uE706" IconFontFamily="Segoe MDL2 Assets.ttf" />
						</radialMenu:SfRadialMenuItem.Items>
					</radialMenu:SfRadialMenuItem>
					<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEBAA" IconFontFamily="Segoe MDL2 Assets.ttf">
						<radialMenu:SfRadialMenuItem.Items>
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEBB8" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEBBC" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uEBC0" IconFontFamily="Segoe MDL2 Assets.ttf" />
						</radialMenu:SfRadialMenuItem.Items>
					</radialMenu:SfRadialMenuItem>
					<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uE7E8"  IconFontFamily="Segoe MDL2 Assets.ttf">
						<radialMenu:SfRadialMenuItem.Items>
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uE708" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uE777" IconFontFamily="Segoe MDL2 Assets.ttf" />
							<radialMenu:SfRadialMenuItem ItemTapped="Handle_ItemTapped" FontIconText="\uE7E8" IconFontFamily="Segoe MDL2 Assets.ttf" />
						</radialMenu:SfRadialMenuItem.Items>
					</radialMenu:SfRadialMenuItem>
				</radialMenu:SfRadialMenu.Items>
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
			radialMenu.CenterButtonBackText = "\uE72B";
			radialMenu.CenterButtonFontFamily = "Segoe MDL2 Assets.ttf";
			radialMenu.CenterButtonBackFontFamily = "Segoe MDL2 Assets.ttf";
			radialMenu.CenterButtonRadius = 32;
			radialMenu.CenterButtonBorderColor = Color.White;

			//Adding RadialMenu items

			string[] layer = new string[] { "\uE701", "\uE702", "\uEA8F", "\uE706", "\uEBAA", "\uE7E8" };
			string[] wifi = new string[] { "\uEC3B", "\uEC3A", "\uEC39", "\uEC38", "\uEC37" };
			string[] battery = new string[] { "\uEBB8", "\uEBBC", "\uEBC0" };
			string[] brightness = new string[] { "\uEC8A", "\uEC8A", "\uE706" };
			string[] profile = new string[] { "\uE7ED", "\uE877", "\uEA8F" };
			string[] power = new string[] { "\uE708", "\uE777", "\uE7E8" };

			//Adding radialMenu main menu items
			for (int i = 0; i < 6; i++)
			{
				SfRadialMenuItem mainMenuItems = new SfRadialMenuItem();
				mainMenuItems.IconFontSize = 20;
				mainMenuItems.FontIconText = layer[i];
				mainMenuItems.ItemHeight = 30;
				mainMenuItems.ItemWidth = 40;
				mainMenuItems.TextColor = Color.White;
				mainMenuItems.ItemTapped += Handle_ItemTapped;
				mainMenuItems.IconFontFamily = "Segoe MDL2 Assets.ttf";
				radialMenu.Items.Add(mainMenuItems);
			}

			// Adding wifi submenu items
			for (int i = 0; i < 5; i++)
			{
				SfRadialMenuItem wifiSubMenuItems = new SfRadialMenuItem();
				wifiSubMenuItems.IconFontSize = 20;
				wifiSubMenuItems.FontIconText = wifi[i];
				wifiSubMenuItems.ItemHeight = 30;
				wifiSubMenuItems.ItemWidth = 40;
				wifiSubMenuItems.TextColor = Color.White;
				wifiSubMenuItems.ItemTapped += Handle_ItemTapped;
				wifiSubMenuItems.IconFontFamily = "Segoe MDL2 Assets.ttf";
				radialMenu.Items[0].Items.Add(wifiSubMenuItems);
			}

			//Adding bluetooth submenu items
			for (int i = 0; i < 5; i++)
			{
				SfRadialMenuItem bluetoothSubMenuItems = new SfRadialMenuItem();
				bluetoothSubMenuItems.IconFontSize = 20;
				bluetoothSubMenuItems.FontIconText = wifi[i];
				bluetoothSubMenuItems.ItemHeight = 30;
				bluetoothSubMenuItems.ItemWidth = 40;
				bluetoothSubMenuItems.TextColor = Color.White;
				bluetoothSubMenuItems.ItemTapped += Handle_ItemTapped;
				bluetoothSubMenuItems.IconFontFamily = "Segoe MDL2 Assets.ttf";
				radialMenu.Items[1].Items.Add(bluetoothSubMenuItems);
			}

			//Adding profile submenu items
			for (int i = 0; i < 3; i++)
			{
				SfRadialMenuItem profileSubMenuItems = new SfRadialMenuItem();
				profileSubMenuItems.IconFontSize = 20;
				profileSubMenuItems.FontIconText = profile[i];
				profileSubMenuItems.ItemHeight = 30;
				profileSubMenuItems.ItemWidth = 40;
				profileSubMenuItems.TextColor = Color.White;
				profileSubMenuItems.ItemTapped += Handle_ItemTapped;
				profileSubMenuItems.IconFontFamily = "Segoe MDL2 Assets.ttf";
				radialMenu.Items[2].Items.Add(profileSubMenuItems);
			}

			//Adding brightness submenu items
			for (int i = 0; i < 3; i++)
			{
				SfRadialMenuItem brightnessSubMenuItems = new SfRadialMenuItem();
				brightnessSubMenuItems.IconFontSize = 20;
				brightnessSubMenuItems.FontIconText = brightness[i];
				brightnessSubMenuItems.ItemHeight = 30;
				brightnessSubMenuItems.ItemWidth = 40;
				brightnessSubMenuItems.TextColor = Color.White;
				brightnessSubMenuItems.IconFontFamily = "Segoe MDL2 Assets.ttf";
				brightnessSubMenuItems.ItemTapped += Handle_ItemTapped;
				radialMenu.Items[3].Items.Add(brightnessSubMenuItems);
			}

			//Adding battery submenu items
			for (int i = 0; i < 3; i++)
			{
				SfRadialMenuItem batterySubMenuItems = new SfRadialMenuItem();
				batterySubMenuItems.IconFontSize = 20;
				batterySubMenuItems.FontIconText = battery[i];
				batterySubMenuItems.ItemHeight = 30;
				batterySubMenuItems.ItemWidth = 40;
				batterySubMenuItems.TextColor = Color.White;
				batterySubMenuItems.IconFontFamily = "Segoe MDL2 Assets.ttf";
				batterySubMenuItems.ItemTapped += Handle_ItemTapped;
				radialMenu.Items[4].Items.Add(batterySubMenuItems);
			}

			//Adding power submenu items
			for (int i = 0; i < 3; i++)
			{
				SfRadialMenuItem powerSubMenuItems = new SfRadialMenuItem();
				powerSubMenuItems.IconFontSize = 20;
				powerSubMenuItems.FontIconText = power[i];
				powerSubMenuItems.ItemHeight = 30;
				powerSubMenuItems.ItemWidth = 40;
				powerSubMenuItems.TextColor = Color.White;
				powerSubMenuItems.IconFontFamily = "Segoe MDL2 Assets.ttf";
				powerSubMenuItems.ItemTapped += Handle_ItemTapped;
				radialMenu.Items[5].Items.Add(powerSubMenuItems);
			}

            this.Content = radialMenu;
	}
}
{% endhighlight %}
{% endtabs %}

{% highlight c# %}
void Handle_ItemTapped(object sender, Syncfusion.SfRadialMenu.XForms.ItemTappedEventArgs e)
	{
		DisplayAlert("ItemTapped", "RadialMenu Item is tapped", "ok");
	}
{% endhighlight %}

![](images/populatingItems.png)

N> To use FontIcons, add respcetive FontFamily name in `info.plist` file under Fonts provided by application category.
