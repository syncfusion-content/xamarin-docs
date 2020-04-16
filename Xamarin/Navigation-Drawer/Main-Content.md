---
layout: post
title: Various features of Syncfusion NavigationDrawer control.
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---


# Main Content of ContentView

Main content of NavigationDrawer is always visible and it can be set using `ContentView` property. In the following code example, ContentView is switched when selection changes in ListView.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" DrawerHeaderHeight="160">
        <navigationdrawer:SfNavigationDrawer.ContentView>
            <Grid x:Name="mainContentView" BackgroundColor="White">
                <Grid.RowDefinitions>
                    <RowDefinition Height="auto"/>
                    <RowDefinition/>
                </Grid.RowDefinitions>
                <StackLayout BackgroundColor="#1aa1d6" Orientation="Horizontal">
                    <Button x:Name="hamburgerButton" HeightRequest="50" WidthRequest="50" HorizontalOptions="Start" FontSize="20" BackgroundColor="#1aa1d6" Clicked="hamburgerButton_Clicked"/>
                    <Label x:Name="headerLabel" HeightRequest="50" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" Text="Home" FontSize="16" TextColor="White" BackgroundColor="#1aa1d6"/>
                </StackLayout>
                <Label Grid.Row="1" x:Name="contentLabel" VerticalOptions="Center" HorizontalOptions="Center" Text="The folder is empty" FontSize="14" TextColor="Black"/>
            </Grid>
        </navigationdrawer:SfNavigationDrawer.ContentView>
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Grid BackgroundColor="#1aa1d6">
                <Grid.RowDefinitions>
                    <RowDefinition Height="120"/>
                    <RowDefinition Height="40"/>
                </Grid.RowDefinitions>
                <Image Source="tab_feed.png" HeightRequest="110" Margin="0,10,0,0" BackgroundColor="#1aa1d6" VerticalOptions="Center" HorizontalOptions="Center"/>
                <Label Text="James Pollock" Grid.Row="1" HorizontalTextAlignment="Center" HorizontalOptions="Center" FontSize="20" TextColor="White"/>
            </Grid>
        </navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
        <navigationdrawer:SfNavigationDrawer.DrawerContentView>
            <ListView x:Name="listView" ItemSelected="listView_ItemSelected">
                <ListView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <StackLayout HeightRequest="40">
                                <Label Margin="10,7,0,0" Text="{Binding}" FontSize="16"/>
                            </StackLayout>
                        </ViewCell>
                    </DataTemplate>
                </ListView.ItemTemplate>
            </ListView>
        </navigationdrawer:SfNavigationDrawer.DrawerContentView>
    </navigationdrawer:SfNavigationDrawer>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

 using System;
using System.Collections.Generic;
using Syncfusion.SfNavigationDrawer.XForms;
using Xamarin.Forms;

namespace NaviSample
{
    public partial class MainPage : ContentPage
    {
        SfNavigationDrawer navigationDrawer = new SfNavigationDrawer() { DrawerHeaderHeight = 160 };
        Label label1;
        public MainPage()
        {
            InitializeComponent();
            Grid grid = new Grid();
            grid.BackgroundColor = Color.White;
            RowDefinition rowDef1 = new RowDefinition() { Height = GridLength.Auto };
            RowDefinition rowDef2 = new RowDefinition() { Height = GridLength.Star };
            grid.RowDefinitions.Add(rowDef1);
            grid.RowDefinitions.Add(rowDef2);

            StackLayout layout = new StackLayout() { BackgroundColor = Color.FromHex("#1aa1d6"), Orientation = StackOrientation.Horizontal };
            var hamburgerButton = new Button
            {
                Text = "StackLayout",
                HeightRequest = 50,
                WidthRequest = 50,
                HorizontalOptions = LayoutOptions.Start,
                FontSize = 20,
                BackgroundColor = Color.FromHex("#1aa1d6")
            };
            hamburgerButton.Clicked += hamburgerButton_Clicked;

            var label = new Label
            {
                HeightRequest = 50,
                HorizontalTextAlignment = TextAlignment.Center,
                VerticalTextAlignment = TextAlignment.Center,
                Text = "Home",
                FontSize = 16,
                TextColor = Color.White,
                BackgroundColor = Color.FromHex("#1aa1d6")
            };
            layout.Children.Add(hamburgerButton);
            layout.Children.Add(label);

            label1 = new Label
            {
                HorizontalOptions = LayoutOptions.Center,
                VerticalOptions = LayoutOptions.Center,
                Text = "Content View",
                FontSize = 14,
                TextColor = Color.Black
            };
            grid.Children.Add(layout, 0, 0);
            grid.Children.Add(label1, 0, 1);
            navigationDrawer.ContentView = grid;

            Grid grid1 = new Grid();
            grid1.BackgroundColor = Color.FromHex("#1aa1d6");
            RowDefinition rowDef3 = new RowDefinition() { Height = 120 };
            RowDefinition rowDef4 = new RowDefinition() { Height = 40 };
            grid1.RowDefinitions.Add(rowDef3);
            grid1.RowDefinitions.Add(rowDef4);

            var image = new Image
            {
                Source = (FileImageSource)ImageSource.FromFile("tab_feed.png"),
                HeightRequest = 110,
                Margin = new Thickness(0, 10, 0, 0),
                BackgroundColor = Color.FromHex("#1aa1d6"),
                HorizontalOptions = LayoutOptions.Center,
                VerticalOptions = LayoutOptions.Center
            };

            var label2 = new Label
            {
                Text = "James Pollock",
                HorizontalTextAlignment = TextAlignment.Center,
                HorizontalOptions = LayoutOptions.Center,
                FontSize = 20,
                TextColor = Color.White
            };
            grid1.Children.Add(image, 0, 0);
            grid1.Children.Add(label2, 0, 1);
            navigationDrawer.DrawerHeaderView = grid1;

            ListView listView = new ListView();
            listView.ItemSelected += listView_ItemSelected;
            StackLayout layout1 = new StackLayout() { HeightRequest = 40 };
            var label3 = new Label
            {
                Margin = new Thickness(10, 7, 0, 0),
                TextColor = Color.Black,
                FontSize = 16,
            };
            label3.SetBinding(Label.TextProperty, "Text");
            navigationDrawer.DrawerContentView = listView;
            this.Content = navigationDrawer;

            navigationDrawer.DrawerWidth = 200;
            hamburgerButton.Image = (FileImageSource)ImageSource.FromFile("burgericon.png");
            List<string> list = new List<string>();
            list.Add("Home");
            list.Add("Profile");
            list.Add("Inbox");
            list.Add("Out box");
            list.Add("Sent");
            list.Add("Draft");
            listView.ItemsSource = list;
        }

        void hamburgerButton_Clicked(object sender, EventArgs e)
        {
            navigationDrawer.ToggleDrawer();
        }

        private void listView_ItemSelected(object sender, SelectedItemChangedEventArgs e)
        {
            if (e.SelectedItem.ToString() == "Home")
                label1.Text = "Home";
            else if (e.SelectedItem.ToString() == "Profile")
                label1.Text = "Profile";
            else if (e.SelectedItem.ToString() == "Inbox")
                label1.Text = "Inbox";
            else if (e.SelectedItem.ToString() == "Out box")
                label1.Text = "Out box";
            else if (e.SelectedItem.ToString() == "Sent")
                label1.Text = "Sent";
            else if (e.SelectedItem.ToString() == "Draft")
                label1.Text = "The folder is empty";
            navigationDrawer.ToggleDrawer();
        }
    }
}
  
{% endhighlight %}

{% endtabs %}

N> It is mandatory to set ContentView for SfNavigationDrawer on initializing.

![contentview](Images/MainContent.png)

You can find the complete Sample from this [link.](https://www.syncfusion.com/downloads/support/directtrac/general/ze/NavigationDrawerMainContent-827989544)