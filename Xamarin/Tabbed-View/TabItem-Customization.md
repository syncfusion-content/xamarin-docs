---
layout: post
title: TabItem Customization in Xamarin Tabbed View | Syncfusion
description: Learn here all about Tabitem Customization support in Syncfusion Xamarin Tabbed View (SfTabView) control and more.
platform: Xamarin
control: TabView
documentation: ug
---

# TabView TabItem Customization in Xamarin Tabbed View (SfTabView)

Tab items can be configured in tab view through the `Items` property of `SfTabView`, which holds the collection of `SfTabItem` through `TabItemsCollection`.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabViewAutomationSample.TabViewAutomationSample">
    <ContentPage.Content>
        <tabView:SfTabView BackgroundColor="White">
            <tabView:SfTabItem Title="Call">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Gray" x:Name="AllContactsGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Favorites">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Green" x:Name="FavoritesGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Contacts">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue" x:Name="ContactsGrid" />
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
        public TabView()
        {
            InitializeComponent();
            var tabView = new SfTabView();
            var allContactsGrid = new Grid { BackgroundColor = Color.Gray };
            var favoritesGrid = new Grid { BackgroundColor = Color.Green };
            var contactsGrid = new Grid { BackgroundColor = Color.Blue };
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
    }
}

{% endhighlight %}

{% endtabs %}

![TabItems](images/TabItems/TabItems.png)

##  Selection color for text and font icons

The selected index can be differentiated by setting the `SelectionColor` property of `SfTabItem`.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabView.TabView">
    <ContentPage.Content>
        <tabView:SfTabView OverflowMode="DropDown"
                            EnableSwiping="false" 
                            VisibleHeaderCount="3">
            <tabView:SfTabItem Title="Call"
                               SelectionColor="Aqua">
                <tabView:SfTabItem.Content>
                    <StackLayout>
                        <Grid BackgroundColor="Green"/>
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
        public TabView()
        {
            InitializeComponent();
            tabView = new SfTabView();
            var allContactsGrid = new Grid { BackgroundColor = Color.Red };
            var favoritesGrid = new Grid { BackgroundColor = Color.Green };
            var contactsGrid = new Grid { BackgroundColor = Color.Blue };
            var overflowButtonSettings = new OverflowButtonSettings();
            overflowButtonSettings.DisplayMode = OverflowButtonDisplayMode.Text;
            overflowButtonSettings.Title = "OverFlow";
            overflowButtonSettings.TitleFontSize = 10;
            tabView.OverflowButtonSettings = overflowButtonSettings;
            tabView.EnableSwiping = false;
            var tabItems = new TabItemCollection
            {
                new SfTabItem()
                {
                    Title = "Calls",
                    Content = allContactsGrid,
                    SelectionColor = Color.Aqua
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
            tabView.OverflowMode = OverflowMode.DropDown;
            this.Content = tabView;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![SelectionColor](images/Display-Type/SelectionColor.png)

The further customizations of header are discussed in the following sections:

## Header title customization

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabView.TabView">
    <ContentPage.Content>
        <tabView:SfTabView OverflowMode="DropDown"
                            EnableSwiping="false" 
                            VisibleHeaderCount="3">
            <tabView:SfTabItem Title="Call"
                               SelectionColor="Aqua">
                <tabView:SfTabItem.Content>
                    <StackLayout>
                        <Grid BackgroundColor="Green"/>
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
            <tabView:SfTabItem Title="Contacts" 
                               TitleFontAttributes="Bold" 
                               TitleFontColor="Red" 
                               TitleFontSize="22">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue" x:Name="ContactsGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Location" 
                               TitleFontAttributes="Bold" 
                               TitleFontColor="Red" 
                               TitleFontSize="22">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Pink" x:Name="LocationGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Email" 
                               TitleFontAttributes="Bold" 
                               TitleFontColor="Red" 
                               TitleFontSize="22">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Navy" x:Name="EmailGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Alternative" 
                               TitleFontAttributes="Bold" 
                               TitleFontColor="Red" 
                               TitleFontSize="22">
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
        public TabView()
        {
            InitializeComponent();
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
                    Content = allContactsGrid,
                    SelectionColor = Color.Aqua
                },
                new SfTabItem()
                {
                    Title = "Favorites",
                    Content = favoritesGrid,
                    TitleFontAttributes = FontAttributes.Bold,
                    TitleFontColor = Color.Red,
                    TitleFontSize = 22
                },
                new SfTabItem()
                {
                    Title = "Contacts",
                    Content = contactsGrid,
                    TitleFontAttributes = FontAttributes.Bold,
                    TitleFontColor = Color.Red,
                    TitleFontSize = 22
                },
                new SfTabItem()
                {
                    Title = "Location",
                    Content = contactsGrid,
                    TitleFontAttributes = FontAttributes.Bold,
                    TitleFontColor = Color.Red,
                    TitleFontSize = 22
                },
                new SfTabItem()
                {
                    Title = "Email",
                    Content = contactsGrid,
                    TitleFontAttributes = FontAttributes.Bold,
                    TitleFontColor = Color.Red,
                    TitleFontSize = 22
                },
                new SfTabItem()
                {
                    Title = "Alternative",
                    Content = contactsGrid,
                    TitleFontAttributes = FontAttributes.Bold,
                    TitleFontColor = Color.Red,
                    TitleFontSize = 22
                }
            };
            tabView.Items = tabItems;
            tabView.BackgroundColor = Color.Aqua;
            tabView.OverflowMode = OverflowMode.DropDown;
            this.Content = tabView;
        }
    }
}

{% endhighlight %}

{% endtabs %}

##  Font icons in the header

You can refer this [link](https://help.syncfusion.com/metro-studio/export-icon-font) for getting the font icons. Add the font file to your application by using the following steps for each platform:

**Adding font file for iOS**

1. Add the font family inside `Resource` folder iOS project.
2. Add the font file with the following build action: `BundleResource`.
3. Update the `Info.plist` file (fonts that are provided by application, UIAppFonts, or key).

**Adding font file for Android**

Add the font file to the `Assets` folder in the application project, and set the following build action: `AndroidAsset`.

**Adding font file for UWP**

Add the font family inside the application project of UWP.

N> For iOS alone, FontFamily property is declared without succeeding with .ttf and for android and UWP platform font family name is defined followed by .ttf.

**Setting font file for font icons**

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TabViewFontSample"
             xmlns:tabview="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabViewFontSample.TabViewFontSamplePage">
    <ContentPage.Resources>
        <ResourceDictionary>
            <OnPlatform x:TypeArguments="x:String" 
                        x:Key="fonts"
                        iOS="OpenTypeFont" 
                        Android="Fonts/OpenTypeFont.ttf" />
            <OnPlatform x:TypeArguments="x:String" 
                        x:Key="fonts" 
                        iOS="Fonts/fa-regular-400" 
                        Android="Fonts/fa-regular-400.ttf" />
        </ResourceDictionary>
    </ContentPage.Resources>
    <ContentPage.Content>
        <Grid BackgroundColor="White" Padding="0,20,0,0">
            <Grid.RowDefinitions>
                <RowDefinition Height="30" />
                <RowDefinition Height="*" />
            </Grid.RowDefinitions>
            <Label Text="Welcome to the Xamarin forms" Grid.Row="0" />
            <tabview:SfTabView Margin="0,0,0,2" 
                               x:Name="SimTab" 
                               VisibleHeaderCount="4" 
                               TabHeaderPosition="Bottom" 
                               DisplayMode="ImageWithText"
                               EnableSwiping="true" 
                               Grid.Row="1" >
                <tabview:SfTabView.Items>
                    <tabview:SfTabItem Title="Chat"   
                                       TitleFontSize="14"
                                       IconFont="A"
                                       FontIconFontFamily="{StaticResource fonts}"
                                       SelectionColor="#FF00AFF0"
                                       FontIconFontColor="#FF00AFF0"
                                       TitleFontColor="#FF00AFF0">
                        <tabview:SfTabItem.Content>
                            <Label Text="Hai" />
                        </tabview:SfTabItem.Content>
                    </tabview:SfTabItem>
                    <tabview:SfTabItem Title="Chat2"   
                                       TitleFontSize="14"
                                       IconFont="&#xf000;"
                                       FontIconFontFamily="{StaticResource fonts}"
                                       SelectionColor="#FF00AFF0"
                                       FontIconFontColor="#FF00AFF0"
                                       TitleFontColor="#FF00AFF0">
                        <tabview:SfTabItem.Content>
                            <Label Text="Hai" />
                        </tabview:SfTabItem.Content>
                    </tabview:SfTabItem>
                    <tabview:SfTabItem Title="like"   
                                       TitleFontSize="14"
                                       IconFont="&#0041;"
                                       FontIconFontFamily="{StaticResource fonts}"
                                       SelectionColor="#FF00AFF0"
                                       FontIconFontColor="#FF00AFF0"
                                       TitleFontColor="#FF00AFF0">
                        <tabview:SfTabItem.Content>
                            <Label Text="Hello"/>
                        </tabview:SfTabItem.Content>
                    </tabview:SfTabItem>
                    <tabview:SfTabItem Title="dislike"   
                                       TitleFontSize="14"
                                       IconFont="&#0041;"
                                       FontIconFontFamily="Fonts/OpenTypeFont.ttf"
                                       SelectionColor="#FF00AFF0"
                                       FontIconFontColor="#FF00AFF0"
                                       TitleFontColor="#FF00AFF0">
                        <tabview:SfTabItem.Content>
                            <Label Text="How are"/>
                        </tabview:SfTabItem.Content>
                    </tabview:SfTabItem>
                    <tabview:SfTabItem Title="status"
                                       TitleFontSize="14"
                                       IconFont="C"
                                       FontIconFontFamily="{StaticResource fonts}"
                                       SelectionColor="#FF00AFF0"
                                       FontIconFontColor="#FF00AFF0"
                                       TitleFontColor="#FF00AFF0">
                        <tabview:SfTabItem.Content>
                            <Label Text="You"/>
                        </tabview:SfTabItem.Content>
                    </tabview:SfTabItem>
                </tabview:SfTabView.Items>
            </tabview:SfTabView>
        </Grid>
    </ContentPage.Content>
</ContentPage>
			
{% endhighlight %}

{% highlight C# %}




using Syncfusion.XForms.TabView;
using Xamarin.Forms;
using Xamarin.Forms.Xaml;

namespace TabViewFontSample
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
    public partial class TabView : ContentPage
    {
        SfTabView tabView;
        public TabView()
        {
            InitializeComponent();
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
                    Content = allContactsGrid,
                    IconFont = "A", // setting value for font icons as mentioned in *.ttf.
	                FontIconFontFamily = Device.RuntimePlatform == "iOS" ? "TabIcons" : Device.RuntimePlatform == "Android" ? "TabIcons.ttf" : "TabIcons.ttf#TabIcons",
                    FontIconFontColor = Color.LightBlue,
                    FontIconFontSize =  20
                },
                new SfTabItem()
                {
                    Title = "Favorites",
                    Content = favoritesGrid,
                    IconFont = "B", // setting value for font icons as mentioned in *.ttf.
	                FontIconFontFamily = Device.RuntimePlatform == "iOS" ? "TabIcons" : Device.RuntimePlatform == "Android" ? "TabIcons.ttf" : "TabIcons.ttf#TabIcons",
                    FontIconFontColor = Color.LightBlue,
                    FontIconFontSize =  20
                },
                new SfTabItem()
                {
                    Title = "Contacts",
                    Content = contactsGrid,
                    IconFont = "C", // setting value for font icons as mentioned in *.ttf.
	                FontIconFontFamily = Device.RuntimePlatform == "iOS" ? "TabIcons" : Device.RuntimePlatform == "Android" ? "TabIcons.ttf" : "TabIcons.ttf#TabIcons",
                    FontIconFontColor = Color.LightBlue,
                    FontIconFontSize =  20
                },
                new SfTabItem()
                {
                    Title = "Alternative",
                    Content = contactsGrid,
                    IconFont = "D", // setting value for font icons as mentioned in *.ttf.
	                FontIconFontFamily = Device.RuntimePlatform == "iOS" ? "TabIcons" : Device.RuntimePlatform == "Android" ? "TabIcons.ttf" : "TabIcons.ttf#TabIcons",
                    FontIconFontColor = Color.LightBlue,
                    FontIconFontSize =  20
                }
            };
            tabView.Items = tabItems;
            tabView.BackgroundColor = Color.Aqua;
            tabView.OverflowMode = OverflowMode.DropDown;
            this.Content = tabView;
        }
    }
}

{% endhighlight %}

{% endtabs %}

You can refer this [link](https://github.com/SyncfusionExamples/tabview-font-sample) for the simple sample defining the tab view items with font icons.

## ImageSource in Xamarin Tabbed View (SfTabView)

The `ImageSource` property customizes the icon image of [Xamarin Tabbed View](https://www.syncfusion.com/xamarin-ui-controls/xamarin-tabbed-view) by adding a custom image.

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
        public TabView()
        {
            InitializeComponent();
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