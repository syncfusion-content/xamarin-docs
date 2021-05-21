---
layout: post
title: Selection Changing in Xamarin Tabbed View control | Syncfusion
description: Learn here all about Selection Changing support in Syncfusion Xamarin Tabbed View (SfTabView) control and more.
platform: Xamarin
control: TabView
documentation: ug
---

# Selection Changing in Xamarin Tabbed View (SfTabView)

## SelectionChanging event

The `SelectionChanging` event is used to notify, before the selection is going to change by swiping, tapping the tab header, and dynamically setting the `SelectedIndex` property of `SfTabView`.

## SelectionChanging event args

`Index` - Gets the value of the index, which is going to be selected.

`Cancel` - Gets or sets the bool value of the tab item, which is going to be selected or not.

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
        public TabView ()
		{
			InitializeComponent ();
            var tabView = new SfTabView();
            tabview.SelectionChanging += Tabview_SelectionChanging;
            Grid allContactsGrid = new Grid {BackgroundColor = Color.Red};
            Grid favoritesGrid = new Grid {BackgroundColor = Color.Green};
            Grid contactsGrid = new Grid {BackgroundColor = Color.Blue};
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
             if (e.Index == 0 || e.Index == 1 || e.Index == 2 || e.Index==3)
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
