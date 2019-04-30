---
layout: post
title: NestedTab with Syncfusion TabView control for Xamarin.Forms 
description: About Nested Tab in TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Nested Tab Items

Nested Tab items can be configured in tab view through the `Items` property of `SfTabView`, which holds the nested collection of `SfTabItem` through `TabItemsCollection`.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:TabViewAutomationSample;assembly=TabViewAutomationSample"
             xmlns:tabview="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             BackgroundColor="#2196F3" x:Name="root"
             xmlns:data="clr-namespace:TabViewAutomationSample"
             x:Class="TabViewAutomationSample.SBNestedTab">
    <ContentPage.Resources>
        <ResourceDictionary>
            <OnPlatform x:TypeArguments="x:String" x:Key="fontfamily" iOS="NestedTab" Android="NestedTab.ttf" />
            <OnPlatform x:TypeArguments="x:String" x:Key="controlfontfamily" iOS="NestedTab" Android="NestedTab.ttf#NestedTab" />
            <data:CustomViewConverter x:Key="nestedtabfont"/>
        </ResourceDictionary>
    </ContentPage.Resources>
    <ContentPage.Content>
        <Grid BackgroundColor="White">
            <tabview:SfTabView EnableSwiping="False"
                               Margin="0,0,0,2" 
                               x:Name="SimTab"
                               VisibleHeaderCount="2" 
                               BackgroundColor="#f1f1f1" >
                <tabview:SfTabView.Items>
                    <tabview:SfTabItem Title="SIM 1"
                                       TitleFontSize="14"
                                       SelectionColor="White"
                                       FontIconFontColor="White"
                                       TitleFontColor="Black">
                        <tabview:SfTabItem.Content>
                            <tabview:SfTabView EnableSwiping="False" 
                                               VisibleHeaderCount="3"
                                               BackgroundColor="#FF00AFF0"
                                               DisplayMode="Image">
                                <tabview:SfTabView.SelectionIndicatorSettings>
                                    <tabview:SelectionIndicatorSettings Color="White"/>
                                </tabview:SfTabView.SelectionIndicatorSettings>
                                <tabview:SfTabView.Items>
                                    <tabview:SfTabItem Title="Recent"
                                                       IconFont="H"
                                                       FontIconFontColor="White"
                                                       TitleFontColor="White"
                                                       SelectionColor="White"
                                                       FontIconFontFamily="{Binding Converter={StaticResource NestedTabFont}}">
                                        <tabview:SfTabItem.Content>
                                            <tabview:SfTabView EnableSwiping="False"
                                                               x:Name="CallsTab1" 
                                                               VisibleHeaderCount="3"
                                                               BackgroundColor="#FFF1F1F1"
                                                               TabHeight="72"
                                                               DisplayMode="ImageWithText"
                                                               TabHeaderPosition="Bottom">
                                                <tabview:SfTabView.Items>
                                                    <tabview:SfTabItem Title="Dialled Calls"
                                                                       IconFont="E"
                                                                       FontIconFontSize="22"
                                                                       FontIconFontFamily="{Binding Converter={StaticResource NestedTabFont}}">
                                                        <tabview:SfTabItem.Content>
                                                                              <Grid BackgroundColor="Gray" x:Name="FavouritesGrid" />
                                                        </tabview:SfTabItem.Content>
                                                    </tabview:SfTabItem>
                                                    <tabview:SfTabItem Title="Received Calls"
                                                                       IconFont="F"
                                                                       FontIconFontSize="22"
                                                                       FontIconFontFamily="{Binding Converter={StaticResource NestedTabFont}}">
                                                        <tabview:SfTabItem.Content>
                                                             <Grid BackgroundColor="Blue" x:Name="ContactsGrid" />
                                                        </tabview:SfTabItem.Content>
                                                    </tabview:SfTabItem>
                                                    <tabview:SfTabItem Title="Missed Calls"
                                                                       IconFont="O"
                                                                       FontIconFontSize="22"
                                                                       FontIconFontFamily="{Binding Converter={StaticResource NestedTabFont}}">
                                                        <tabview:SfTabItem.Content>
                                                            <Grid BackgroundColor="Olive" x:Name="EmailGrid" />
                                                        </tabview:SfTabItem.Content>
                                                    </tabview:SfTabItem>
                                                </tabview:SfTabView.Items>
                                            </tabview:SfTabView >
                                        </tabview:SfTabItem.Content>
                                    </tabview:SfTabItem>
                                    <tabview:SfTabItem Title="Favorites"
                                                       IconFont="Z"
                                                       FontIconFontColor="White"
                                                       TitleFontColor="White"
                                                       SelectionColor="White"
                                                       FontIconFontFamily="{Binding Converter={StaticResource NestedTabFont}}">
                                        <tabview:SfTabItem.Content>
                                            <Grid BackgroundColor="Green" x:Name="NativeGrid" />
                                        </tabview:SfTabItem.Content>
                                    </tabview:SfTabItem>
                                    <tabview:SfTabItem Title="Contacts"
                                                       IconFont="N"
                                                       FontIconFontColor="White"
                                                       TitleFontColor="White"
                                                       SelectionColor="White"
                                                       FontIconFontFamily="{Binding Converter={StaticResource NestedTabFont}}">
                                        <tabview:SfTabItem.Content>
                                            <tabview:SfTabView EnableSwiping="False" 
                                                               VisibleHeaderCount="2"
                                                               x:Name="ContactTab1"
                                                               DisplayMode="ImageWithText"
                                                               TabHeight="72"
                                                               BackgroundColor="White"
                                                               TabHeaderPosition="Bottom">
                                                <tabview:SfTabView.Items>
                                                    <tabview:SfTabItem Title="All Contacts"
                                                                       IconFont="f"
                                                                       FontIconFontSize="22"
                                                                       FontIconFontFamily="{Binding Converter={StaticResource NestedTabFont}}">
                                                        <tabview:SfTabItem.Content>
                                                            <Grid BackgroundColor="Green" />
                                                        </tabview:SfTabItem.Content>
                                                    </tabview:SfTabItem>
                                                    <tabview:SfTabItem Title="Speed Dial"
                                                                       IconFont="g"
                                                                       FontIconFontSize="22"
                                                                       FontIconFontFamily="{Binding Converter={StaticResource NestedTabFont}}">
                                                        <tabview:SfTabItem.Content> 
                                                            <Grid BackgroundColor="Olive" />
                                                        </tabview:SfTabItem.Content>
                                                    </tabview:SfTabItem>
                                                </tabview:SfTabView.Items>
                                            </tabview:SfTabView >
                                        </tabview:SfTabItem.Content>
                                    </tabview:SfTabItem>
                                </tabview:SfTabView.Items>
                            </tabview:SfTabView>
                        </tabview:SfTabItem.Content>
                    </tabview:SfTabItem>
                    <tabview:SfTabItem Title="SIM 2"
                                       TitleFontSize="14"
                                       SelectionColor="White"
                                       FontIconFontColor="White"
                                       TitleFontColor="Black">
                        <tabview:SfTabItem.Content>
                            <Grid BackgroundColor="Olive" />
                        </tabview:SfTabItem.Content>
                    </tabview:SfTabItem>
                </tabview:SfTabView.Items>
            </tabview:SfTabView>
        </Grid>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using System;
using System.Collections.Generic;
using System.Globalization;
using Syncfusion.XForms.TabView;
using Xamarin.Forms;

namespace TabViewAutomationSample
{
    public partial class SBNestedTab : ContentPage
    {
        public SBNestedTab()
        {
            InitializeComponent();
        }
    }
    public class CustomViewConverter : IValueConverter
    {
        public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
        {
            if (Device.RuntimePlatform == "Android")
            {
                if (parameter != null && parameter is string)
                {
                    return "NestedTab.ttf#" + parameter.ToString();
                }
                else
                {
                    return "NestedTab.ttf";
                }
            }
            else if (Device.RuntimePlatform == "iOS")
            {
                return "NestedTab";
            }
            else
            {
                return "/Assets/Fonts/NestedTab.ttf#NestedTab";
            }
        }
        public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
        {
            throw new NotImplementedException();
        }
    }
    public class CustomFrame : Frame
    {
        
    }
}

{% endhighlight %}

{% endtabs %}

![NestedTab Image](images/NestedTab/NestedTab.png)