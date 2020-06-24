---
layout: post
title: Header Positioning for Syncfusion SfTabView Control
description: Learn about position of header support in Syncfusion Xamarin Tabbed View (SfTabView) control and more details.
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Positioning of header in Xamarin Tabbed View (SfTabView)

Tab headers can be positioned either above the content or below the content. This can be done by setting the `TabHeaderPosition` property of `SfTabView`.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabView.TabView">
    <ContentPage.Content>
        <tabView:SfTabView VisibleHeaderCount="3"
                           TabHeaderPosition="Bottom"  
                           OverflowMode="DropDown">
            <tabView:SfTabItem Title="CEO">
                <tabView:SfTabItem.Content>
                    <StackLayout>
                        <Grid BackgroundColor="Green"/>
                        <Button Text="Contacts" WidthRequest="300" />
                        <Button Text="Location" WidthRequest="300" />
                        <Button Text="Email" WidthRequest="300" />
                    </StackLayout>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Patients">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue" x:Name="FavoritesGrid"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Staff">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Green" x:Name="ContactsGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Alternative">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Olive" x:Name="AlternativeGrid" />
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
            var favoritesGrid = new Grid { BackgroundColor = Color.Blue };
            var contactsGrid = new Grid { BackgroundColor = Color.Green };
            var alternativeGrid = new Grid { BackgroundColor = Color.Olive };
            tabView.TabHeaderPosition = TabHeaderPosition.Bottom;
            tabView.OverflowMode = OverflowMode.DropDown;
            var tabItems = new TabItemCollection
            {
                new SfTabItem()
                {
                    Title = "CEO",
                    Content = allContactsGrid
                },
                new SfTabItem()
                {
                    Title = "Patients",
                    Content = favoritesGrid
                },
                new SfTabItem()
                {
                    Title = "Staff",
                    Content = contactsGrid
                }
                new SfTabItem()
                {
                    Title = "Alternative",
                    Content = alternativeGrid
                }
            };
            tabView.Items = tabItems;
            this.Content = tabView;
		}
	}
}
			
{% endhighlight %}

{% endtabs %}

When the header is not needed, set the `DisplayMode` property of `SfTabView` to `NoHeader`.

![Positioning of Header](images/Position-of-Header/HeaderPosition.png)