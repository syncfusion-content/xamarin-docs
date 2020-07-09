---
layout: post
title: Image Source Support for Syncfusion TabView Control
description: Provides support for Image Source & Font Image Source support in SfTabItem headers for adding custom images. 
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Image source in SfTabItem

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

## FontImageSource in SfTabItem

The `FontImageSource` property provide a custom font image source to the image source of tab items headers in the Tab View control.

{% tabs %}

{% highlight xaml %}

  <ContentPage.Resources>
        <ResourceDictionary>
            <OnPlatform x:TypeArguments="x:String" x:Key="AwsomeIcon">
                <On Platform="Android" Value="Sync FontIcons.ttf#" />
                <On Platform="UWP" Value="Sync FontIcons.ttf#Sync FontIcons" />
                <On Platform="iOS" Value="Sync FontIcons" />
            </OnPlatform>
            <FontImageSource x:Key="Icon_1"
                             FontFamily="{StaticResource AwsomeIcon}" 
                             Glyph="&#xe747;"
                             Color="Red" />
            <FontImageSource x:Key="Icon_2" 
                             FontFamily="{StaticResource AwsomeIcon}" 
                             Glyph="&#xe708;"
                             Color="DarkViolet" />
            <FontImageSource x:Key="Icon_3" 
                             FontFamily="{StaticResource AwsomeIcon}" 
                             Glyph="&#xe702;"
                             Color="Blue" />
      </ResourceDictionary>
</ContentPage.Resources>
    <StackLayout>
        <tabView:SfTabView  
                         x:Name="tabView"  
                         DisplayMode="ImageWithText" 
                         BackgroundColor="White" 
                         VisibleHeaderCount="3"
                         HorizontalOptions="FillAndExpand"
                         VerticalOptions="FillAndExpand">
            <tabView:SfTabItem Title="Mail" ImageSource="{StaticResource Icon_1}">
                <tabView:SfTabItem.Content>
                      <StackLayout x:Name="AllContactsGrid" >
                        <Image Source="mail.png" HorizontalOptions="Center" VerticalOptions="CenterAndExpand"/>
                    </StackLayout>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Camera" ImageSource="{StaticResource Icon_2}">
                <tabView:SfTabItem.Content>
                     <Grid BackgroundColor="Green" x:Name="AllContactsGrid1" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Downloads" ImageSource="{StaticResource Icon_3}">
                <tabView:SfTabItem.Content>
                      <Grid BackgroundColor="Yellow" x:Name="AllContactsGrid2" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            </tabView:SfTabView>
    </StackLayout>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.XForms.TabView;
using System;
using Xamarin.Forms;
namespace SfTabViewSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            SfTabView tabView;
            InitializeComponent();
            tabView = new SfTabView();
            tabView.VisibleHeaderCount = 3;
            tabView.DisplayMode = TabDisplayMode.ImageWithText;
            FontImageSource fontImageSource = new FontImageSource();
            fontImageSource.FontFamily = Device.RuntimePlatform == Device.Android ? "Sync FontIcons.ttf#Sync FontIcons" : Device.RuntimePlatform == Device.iOS ? "Sync FontIcons" : "Sync FontIcons.ttf#Sync FontIcons";
            fontImageSource.Color = Color.Red;
            fontImageSource.Glyph = "\ue747";

            FontImageSource fontImageSource1 = new FontImageSource();
            fontImageSource1.FontFamily = Device.RuntimePlatform == Device.Android ? "Sync FontIcons.ttf#Sync FontIcons" : Device.RuntimePlatform == Device.iOS ? "Sync FontIcons" : "Sync FontIcons.ttf#Sync FontIcons";
            fontImageSource1.Color = Color.Red;
            fontImageSource1.Glyph = "\ue708";

            FontImageSource fontImageSource2 = new FontImageSource();
            fontImageSource2.FontFamily = Device.RuntimePlatform == Device.Android ? "Sync FontIcons.ttf#Sync FontIcons" : Device.RuntimePlatform == Device.iOS ? "Sync FontIcons" : "Sync FontIcons.ttf#Sync FontIcons";
            fontImageSource2.Color = Color.Red;
            fontImageSource2.Glyph = "\ue702";

            var allContactsGrid = new StackLayout();
            var image = new Image { Source = "mail.png", HorizontalOptions = LayoutOptions.Center, VerticalOptions = LayoutOptions.CenterAndExpand };
            allContactsGrid.Children.Add(image);
            var favoritesGrid = new Grid { BackgroundColor = Color.Green };
            var contactsGrid = new Grid { BackgroundColor = Color.Blue };
            var emailGrid = new Grid { BackgroundColor = Color.Blue };
            var tabItems = new TabItemCollection
            {
                new SfTabItem()
                {
                    Title = "Mail",
                    Content = allContactsGrid,
                    ImageSource = fontImageSource,
                },
                new SfTabItem()
                {
                    Title = "Camera",
                    Content = favoritesGrid,
                    ImageSource = fontImageSource1
                },
                new SfTabItem()
                {
                    Title = "Downloads",
                    Content = contactsGrid,
                    ImageSource = fontImageSource2,
                },
            };

            tabView.Items = tabItems;
            this.Content = tabView;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### How to set and customize the font icons' appearance in the header?

You can refer this [link](https://help.syncfusion.com/metro-studio/export-font-icon) for getting the font icons. Add the font file to your application by using the following steps for each platform:

**Adding font file for iOS**

1. Add the font family inside `Resource` folder iOS project.
2. Add the font file with the following build action: `BundleResource`.
3. Update the `Info.plist` file (fonts that are provided by application, UIAppFonts, or key).

**Adding font file for Android**

Add the font file to the `Assets` folder in the application project, and set the following build action: `AndroidAsset`.

**Adding font file for UWP**

Add the font family inside the application project of UWP.

N> For iOS alone, FontFamily property is declared without succeeding with .ttf and for android and UWP platform font family name is defined followed by .ttf.

![FontImageSource](images/ImageSource/FontImageSource.png)