---
layout: post
title: TabView Events in Xamarin Tabbed View control | Syncfusion
description: Learn here all about TabView Events support in Syncfusion Xamarin Tabbed View (SfTabView) control and more.
platform: Xamarin
control: TabView
documentation: ug
---

# TabView Events in Xamarin Tabbed View (SfTabView)

## TabItem Tapped in Xamarin Tabbed View (SfTabView)

Whenever the TabItem is tapped, the [`TabItemTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_TabItemTapped) event will occur. Using this event, you can modify the selected Tab Item properties.

{% tabs %}

{% highlight xaml %}

<ContentPage.Content>
    <StackLayout>
        <tabView:SfTabView x:Name="tabView" VerticalOptions="FillAndExpand"
                           TabItemTapped="TabView_TabItemTapped"
                           VisibleHeaderCount="3">
            <tabView:SfTabItem Title="Call">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="LightGreen" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Favorites">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="LightBlue"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Contacts">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="LightGreen" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
        </tabView:SfTabView>
    </StackLayout>
</ContentPage.Content>

{% endhighlight %}

{% highlight C# %}

public MainPage()
{
    InitializeComponent();
    tabView.TabItemTapped += TabView_TabItemTapped;
}

private void TabView_TabItemTapped(object sender, Syncfusion.XForms.TabView.TabItemTappedEventArgs e)
{
    DisplayAlert("TabViewItemTapped", e.TabItem.Title + " Item Tapped", "Ok");
}

{% endhighlight %}

{% endtabs %}

Note: Please refer to this [Link](https://www.syncfusion.com/kb/11562/how-to-turn-events-into-commands-with-behaviors-in-xamarin-forms-tabbed-view) for how to turn Events into Commands with Behaviors in Xamarin.Forms Tabbed View.

## SelectionChanging in Xamarin Tabbed View (SfTabView)

The [`SelectionChanging`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_SelectionChanging) event is used to notify, before the selection is going to change by swiping, tapping the tab header, and dynamically setting the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_SelectedIndex) property of [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html).

### SelectionChanging event args

[`Index`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SelectionChangingEventArgs.html#Syncfusion_XForms_TabView_SelectionChangingEventArgs_Index) - Gets the value of the index that will be selected.

[`Cancel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SelectionChangingEventArgs.html#Syncfusion_XForms_TabView_SelectionChangingEventArgs_Cancel)- Gets or sets the bool value of the tab item that will be selected or not.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Syncfusion.XForms.TabView"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabView.TabView">
    <ContentPage.Content>
        <tabView:SfTabView VisibleHeaderCount="3" 
                           SelectionChanging="Tabview_SelectionChanging"
                           BackgroundColor="Aqua">
            <tabView:SfTabItem Title="Call">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Red"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Favorites">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Green"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Contacts">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Location">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Pink"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Email">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Navy"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Alternative">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue"/>
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
		public TabView()
		{
			InitializeComponent();
			var tabView = new SfTabView();
			tabview.SelectionChanging += Tabview_SelectionChanging;
			Grid allContactsGrid = new Grid { BackgroundColor = Color.Red };
			Grid favoritesGrid = new Grid { BackgroundColor = Color.Green };
			Grid contactsGrid = new Grid { BackgroundColor = Color.Blue };
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
				}
			};
			tabView.Items = tabItems;
			this.Content = tabView;
		}

		// Occurred when the index is going to be changed.
		void Tabview_SelectionChanging(object sender, Syncfusion.XForms.TabView.SelectionChangingEventArgs e)
		{
			if (e.Index == 0 || e.Index == 1 || e.Index == 2 || e.Index == 3)
			{
				e.Cancel = false;
			}
			else
			{
				e.Cancel = true;
			}
		}
	}
}


{% endhighlight %}

{% endtabs %}


## Selection Changed in Xamarin Tabbed View (SfTabView)

The [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_SelectionChanged) event is used to notify when the selection is changed by swiping or dynamically setting the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_SelectedIndex)  property of [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Syncfusion.XForms.TabView"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabView.TabView">
    <ContentPage.Content>
        <tabView:SfTabView VisibleHeaderCount="3" 
                           SelectionChanged="Handle_SelectionChanged"
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
        public TabView()
        {
            InitializeComponent();
        }

        // Occurred when the selected index is changed
        void Handle_SelectionChanged(object sender, Syncfusion.XForms.TabView.SelectionChangedEventArgs e)
        {
            var selectedIndex = e.Index;
        }
    }
}

{% endhighlight %}

{% endtabs %}


