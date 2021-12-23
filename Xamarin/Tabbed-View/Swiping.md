---
layout: post
title: Swiping in Xamarin Tabbed View | Syncfusion
description: Learn here all about swiping support in Syncfusion Xamarin Tabbed View (SfTabView) control and more.
platform: Xamarin
control: TabView
documentation: ug
---

# Swiping in Xamarin Tabbed View (SfTabView)

By default, both the vertical swiping for list view and horizontal swiping for tab view will work.

## Enable swiping

Swiping can be customized by using the [`EnableSwiping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_EnableSwiping) property of SfTabView. By default, [`EnableSwiping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_EnableSwiping) is set to true. To limit the user interaction, set the   
[`EnableSwiping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_EnableSwiping) property of SfTabView to false.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabView.TabView">
    <ContentPage.Content>
         <tabView:SfTabView OverflowMode="DropDown"
                            EnableSwiping="false" 
                            VisibleHeaderCount="3" 
                            BackgroundColor="Aqua">
            <tabView:SfTabItem Title="Call">
                <tabView:SfTabItem.Content>
                    <StackLayout>
                        <Grid BackgroundColor="Green" />
                        <Button Text="Contacts" WidthRequest="300" />
                        <Button Text="Location" WidthRequest="300" />
                        <Button Text="Email" WidthRequest="300" />
                    </StackLayout>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Favorites">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Green" x:Name="FavoritesGrid"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Contacts">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue" x:Name="ContactsGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Location">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Pink" x:Name="LocationGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Email">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Navy" x:Name="EmailGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Alternative">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue" x:Name="AlternativeGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
        </tabView:SfTabView>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.XForms.TabView;
using Xamarin.Forms;
using Xamarin.Forms.Xaml;

namespace TabView
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
	public partial class TabView : ContentPage
	{
        SfTabView tabView;
		public TabView ()
		{
			InitializeComponent ();
            tabView = new SfTabView();
            var allContactsGrid = new Grid { BackgroundColor = Color.Red };
            var favoritesGrid = new Grid { BackgroundColor = Color.Green };
            var contactsGrid = new Grid { BackgroundColor = Color.Blue };
            var overflowButtonSettings = new OverflowButtonSettings();
            overflowButtonSettings.BackgroundColor = Color.Yellow;
            overflowButtonSettings.DisplayMode = OverflowButtonDisplayMode.Text;
            overflowButtonSettings.Title = "OverFlow";
            overflowButtonSettings.TitleFontSize = 10;
            overflowButtonSettings.TitleFontColor = Color.Blue;
            tabView.OverflowButtonSettings = overflowButtonSettings;
            tabView.EnableSwiping = false;
            var tabItems = new TabItemCollection
            {
                new SfTabItem()
                {
                    Title = "Calls",
                    Content = allContactsGrid
                },
                new SfTabItem()
                {
                    Title = "Favorites",
                    Content = favoritesGrid
                },
                new SfTabItem()
                {
                    Title = "Contacts",
                    Content = contactsGrid
                },
                new SfTabItem()
                {
                    Title = "Location",
                    Content = contactsGrid
                },
                new SfTabItem()
                {
                    Title = "Email",
                    Content = contactsGrid
                },
                new SfTabItem()
                {
                    Title = "Alternative",
                    Content = contactsGrid
                }
            };
            tabView.Items = tabItems;
            this.Content = tabView;
            tabView.BackgroundColor = Color.Aqua;
            tabView.OverflowMode = OverflowMode.DropDown;
            this.Content = tabView;
		}
	}
}

{% endhighlight %}

{% endtabs %}

## SwipingThreshold

By setting the [`SwipingThreshold`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_SwipingThreshold), you can set how far swipe before it is considered a swipe.

{% tabs %}

{% highlight xaml %}

    <tabView:SfTabView SwipingThreshold="30" EnableSwiping="True">
    ...
    </tabView:SfTabView>

{% endhighlight %}

{% highlight C# %}

     ...
     tabView.EnableSwiping = true;
     tabView.SwipingThreshold = 30;
     ...
{% endhighlight %}

{% endtabs %}

N> This SwipingThreshold value should only be considered for swiping from left to right.

## AnimationDuration

When the selected index of the control is changed, you can set the speed of the animation of SelectionIndicator by setting the `AnimationDuration` property in the [SelectionIndicatorSettings](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SelectionIndicatorSettings.html).

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabView.TabView">
    <ContentPage.Content>
        <tabView:SfTabView>
            <tabView:SfTabView.SelectionIndicatorSettings>
                <tabView:SelectionIndicatorSettings
                    Color="Red" 
                    Position="Top" 
                    AnimationDuration="500"
                    StrokeThickness="5"/>
            </tabView:SfTabView.SelectionIndicatorSettings>
            <tabView:SfTabItem Title="Call">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Green"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Favorites">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Green"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Contacts">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
        </tabView:SfTabView>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.XForms.TabView;
using Xamarin.Forms;
using Xamarin.Forms.Xaml;

namespace TabView
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
	public partial class TabView : ContentPage
	{
        SfTabView tabView;
		public TabView ()
		{
			InitializeComponent ();
            tabView = new SfTabView();
            var selectionIndicatorSettings = new SelectionIndicatorSettings();
            selectionIndicatorSettings.Color = Color.Red;
            selectionIndicatorSettings.Position = SelectionIndicatorPosition.Bottom;
            selectionIndicatorSettings.StrokeThickness = 5;
            selectionIndicatorSettings.AnimationDuration = 500;
            tabView.SelectionIndicatorSettings = selectionIndicatorSettings;
            tabView.TabHeaderPosition = TabHeaderPosition.Top;
            tabView.OverflowMode = OverflowMode.Scroll;
            var allContactsGrid = new Grid { BackgroundColor = Color.Aqua };
            var favoritesGrid = new Grid { BackgroundColor = Color.Green };
            var contactsGrid = new Grid { BackgroundColor = Color.Blue };
            var tabItems = new TabItemCollection
            {
               new tabview.SfTabItem()
                {
                Title = "Calls",
                Content = allContactsGrid
                },
                new tabview.SfTabItem()
                {
                    Title = "Favorites",
                    Content = favoritesGrid
                },
                new tabview.SfTabItem()
                {
                    Title = "Contacts",
                    Content = contactsGrid
                }               
            };
            tabView.Items = tabItems;
            this.Content = tabView;
		}
	}
}

{% endhighlight %}

{% endtabs %}

![Animation Duration](images/Selection-Indicator/AnimationDuration.gif)


