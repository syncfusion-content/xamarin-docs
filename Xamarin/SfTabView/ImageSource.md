---
layout: post
title: Image Source Support for Syncfusion TabView Control
description: About Tab items in TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Image Source

The `ImageSource` property customizes the icon image of SfTabView by adding a custom image.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabViewAutomationSample.TabViewAutomationSample">
    <ContentPage.Content>
        <tabView:SfTabView BackgroundColor="Aqua" VisibleHeaderCount="3" DisplayMode="ImageWithText">
            <tabView:SfTabItem Title="Call" ImageSource="phone.png">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Red" x:Name="AllContactsGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Favorites" ImageSource="home.png">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Green" x:Name="FavoritesGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Contacts" ImageSource="review.png">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue" x:Name="ContactsGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Email" ImageSource="notifications.png">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Olive" x:Name="EmailGrid" />
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

namespace TabViewAutomationSample
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
	public partial class TabView : ContentPage
	{
        SfTabView tabView;
		public TabView ()
		{
			InitializeComponent ();
            var tabView = new SfTabView();
            var allContactsGrid = new Grid { BackgroundColor = Color.Red };
            var favoritesGrid = new Grid { BackgroundColor = Color.Green };
            var contactsGrid = new Grid { BackgroundColor = Color.Blue };
            var emailGrid = new Grid { BackgroundColor = Color.Blue };
            var tabItems = new TabItemCollection
            {
                new SfTabItem()
                {
                    Title = "Calls",
                    Content = allContactsGrid,
                    ImageSource = "phone.png"
                },
                new SfTabItem()
                {
                    Title = "Favorites",
                    Content = favoritesGrid,
                    ImageSource = "home.png"

                },
                new SfTabItem()
                {
                    Title = "Contacts",
                    Content = contactsGrid,
                    ImageSource = "review.png"
                },
                new SfTabItem()
                {
                    Title = "Email",
                    Content = EmailGrid,
                    ImageSource = "notification.png"
                }
            };
            tabView.Items = tabItems;
            this.Content = tabView;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![ImageSource](images/ImageSource/ImageSource.png)