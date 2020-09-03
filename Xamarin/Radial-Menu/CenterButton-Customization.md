---
layout: post
title: Center button with  Syncfusion RadialMenu control in Xamarin.Forms
description: Working with various options available in SfRadialMenuItems in Xamarin.Forms
platform: Xamarin
control: SfRadialMenu
documentation: ug
---

# CenterButton Customization

The CenterButton or BackButton in radial menu is a view in the center of the radial menu. It performs the operations such as opening and closing the rim and navigating to next level items. The radial menu allows you customize the CenterButton/BackButton with `FontIcon`, `Custom View`, and `Caption`.

## CenterButtonText and CenterButtonBackText

The [`CenterButtonText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonTextProperty) changes the text of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html), and the [`CenterButtonBackText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonBackTextProperty) changes the text of the center back button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu CenterButtonText="&#xe700;"
                             CenterButtonBackText="&#xe72b;">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonText = "\uE700",
                CenterButtonBackText = "\uE72b"
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## CenterButtonTextColor and CenterButtonBackTextColor

The [`CenterButtonTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonTextColorProperty) changes the text color of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html), and the [`CenterButtonBackTextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonBackTextColorProperty) changes the text color of the center back button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu CenterButtonText="&#xe700;"
                             CenterButtonBackText="&#xe72b;"
                             CenterButtonTextColor="#000000"
                             CenterButtonBackTextColor="#000000">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>

    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonText = "\uE700",
                CenterButtonBackText = "\uE72b",
                CenterButtonTextColor = Color.FromHex("#000000"),
                CenterButtonBackTextColor = Color.FromHex("#000000")
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## CenterButtonBackgroundColor

The [`CenterButtonBackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonBackgroundColorProperty) changes the background color of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu  CenterButtonBackgroundColor="#000000">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonBackgroundColor = Color.FromHex("#000000")
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## CenterButtonRadius

The [`CenterButtonRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonRadiusProperty) changes the radius of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu  CenterButtonRadius="5">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonRadius = 5
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## CenterButtonFontFamily and CenterButtonBackFontFamily

The [`CenterButtonFontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonFontFamilyProperty) changes the font family of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html), and the [`CenterButtonBackFontFamily`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonBackFontFamilyProperty) changes the font family of the center back button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <ContentPage.Resources>
        <ResourceDictionary>
            <OnPlatform x:TypeArguments="x:String" 
                        x:Key="customfontfamily" 
                        iOS="Segoe MDL2 Assets" 
                        Android="radialmenu_Segoe MDL2 Assets.ttf" 
                        UWP="radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"  />
        </ResourceDictionary>
    </ContentPage.Resources>
    <radialMenu:SfRadialMenu CenterButtonText="&#xe700;"
                             CenterButtonBackText="&#xe72b;"
                             CenterButtonTextColor="#000000"
                             CenterButtonBackTextColor="#000000"
                             CenterButtonFontFamily="{StaticResource customfontfamily}" 
                             CenterButtonBackFontFamily="{StaticResource customfontfamily}">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonText = "\uE700",
                CenterButtonBackText = "\uE72b",
                CenterButtonTextColor = Color.FromHex("#000000"),
                CenterButtonBackTextColor = Color.FromHex("#000000"),
                CenterButtonFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonBackFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## CenterButtonFontSize and CenterButtonBackFontSize

The [`CenterButtonFontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonFontSizeProperty) changes the font size of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html), and the [`CenterButtonBackFontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonBackFontSizeProperty) changes the font size of the center back button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <ContentPage.Resources>
        <ResourceDictionary>
            <OnPlatform x:TypeArguments="x:String" 
                        x:Key="customfontfamily" 
                        iOS="Segoe MDL2 Assets" 
                        Android="radialmenu_Segoe MDL2 Assets.ttf" 
                        UWP="radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"  />
        </ResourceDictionary>
    </ContentPage.Resources>
    <radialMenu:SfRadialMenu CenterButtonText="&#xe700;"
                             CenterButtonBackText="&#xe72b;"
                             CenterButtonTextColor="#000000"
                             CenterButtonBackTextColor="#000000"
                             CenterButtonFontFamily="{StaticResource customfontfamily}" 
                             CenterButtonBackFontFamily="{StaticResource customfontfamily}"
                             CenterButtonFontSize="10" 
                             CenterButtonBackFontSize="10">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonText = "\uE700",
                CenterButtonBackText = "\uE72b",
                CenterButtonTextColor = Color.FromHex("#000000"),
                CenterButtonBackTextColor = Color.FromHex("#000000"),
                CenterButtonFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonBackFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonFontSize = 10,
                CenterButtonBackFontSize = 10
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## CenterButtonFontAttributes

The [`CenterButtonFontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonFontAttributesProperty) changes the font attributes of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <ContentPage.Resources>
        <ResourceDictionary>
            <OnPlatform x:TypeArguments="x:String" 
                        x:Key="customfontfamily" 
                        iOS="Segoe MDL2 Assets" 
                        Android="radialmenu_Segoe MDL2 Assets.ttf" 
                        UWP="radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"  />
        </ResourceDictionary>
    </ContentPage.Resources>
    <radialMenu:SfRadialMenu CenterButtonText="&#xe700;"
                             CenterButtonBackText="&#xe72b;"
                             CenterButtonTextColor="#000000"
                             CenterButtonBackTextColor="#000000"
                             CenterButtonFontFamily="{StaticResource customfontfamily}" 
                             CenterButtonBackFontFamily="{StaticResource customfontfamily}"
                             CenterButtonFontSize="10" 
                             CenterButtonBackFontSize="10"
                             CenterButtonFontAttributes="Bold">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonText = "\uE700",
                CenterButtonBackText = "\uE72b",
                CenterButtonTextColor = Color.FromHex("#000000"),
                CenterButtonBackTextColor = Color.FromHex("#000000"),
                CenterButtonFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonBackFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonFontSize = 10,
                CenterButtonBackFontSize = 10,
                CenterButtonFontAttributes = FontAttributes.Bold
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## CenterButtonBorderColor

The [`CenterButtonBorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonBorderColorProperty) changes the border color of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <ContentPage.Resources>
        <ResourceDictionary>
            <OnPlatform x:TypeArguments="x:String" 
                        x:Key="customfontfamily" 
                        iOS="Segoe MDL2 Assets" 
                        Android="radialmenu_Segoe MDL2 Assets.ttf" 
                        UWP="radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"  />
        </ResourceDictionary>
    </ContentPage.Resources>
    <radialMenu:SfRadialMenu CenterButtonText="&#xe700;"
                             CenterButtonBackText="&#xe72b;"
                             CenterButtonTextColor="#000000"
                             CenterButtonBackTextColor="#000000"
                             CenterButtonFontFamily="{StaticResource customfontfamily}" 
                             CenterButtonBackFontFamily="{StaticResource customfontfamily}"
                             CenterButtonFontSize="10" 
                             CenterButtonBackFontSize="10"
                             CenterButtonFontAttributes="Bold"
                             CenterButtonBorderColor="Black">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonText = "\uE700",
                CenterButtonBackText = "\uE72b",
                CenterButtonTextColor = Color.FromHex("#000000"),
                CenterButtonBackTextColor = Color.FromHex("#000000"),
                CenterButtonFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonBackFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonFontSize = 10,
                CenterButtonBackFontSize = 10,
                CenterButtonFontAttributes = FontAttributes.Bold,
                CenterButtonBorderColor = Color.Black
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## CenterButtonBorderThickness

The [`CenterButtonBorderThickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonBorderThicknessProperty) changes the border thickness of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <ContentPage.Resources>
        <ResourceDictionary>
            <OnPlatform x:TypeArguments="x:String" 
                        x:Key="customfontfamily" 
                        iOS="Segoe MDL2 Assets" 
                        Android="radialmenu_Segoe MDL2 Assets.ttf" 
                        UWP="radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"  />
        </ResourceDictionary>
    </ContentPage.Resources>
    <radialMenu:SfRadialMenu CenterButtonText="&#xe700;"
                             CenterButtonBackText="&#xe72b;"
                             CenterButtonTextColor="#000000"
                             CenterButtonBackTextColor="#000000"
                             CenterButtonFontFamily="{StaticResource customfontfamily}" 
                             CenterButtonBackFontFamily="{StaticResource customfontfamily}"
                             CenterButtonFontSize="10" 
                             CenterButtonBackFontSize="10"
                             CenterButtonFontAttributes="Bold"
                             CenterButtonBorderColor="Black"
                             CenterButtonBorderThickness="2">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonText = "\uE700",
                CenterButtonBackText = "\uE72b",
                CenterButtonTextColor = Color.FromHex("#000000"),
                CenterButtonBackTextColor = Color.FromHex("#000000"),
                CenterButtonFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonBackFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonFontSize = 10,
                CenterButtonBackFontSize = 10,
                CenterButtonFontAttributes = FontAttributes.Bold,
                CenterButtonBorderColor = Color.Black,
                CenterButtonBorderThickness = 2
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## CenterButtonPlacement

The [`CenterButtonPlacement`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonPlacementProperty) changes the placement of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html)

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu CenterButtonPlacement="Center">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonPlacement = SfRadialMenuCenterButtonPlacement.Center
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Center button view and center back button view

You can customize the center button using [`CenterButtonView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonViewProperty)and center back button using [`CenterButtonBackView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_CenterButtonBackViewProperty) in  [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu x:Name="radialMenu">
        <radialMenu:SfRadialMenu.CenterButtonView >
            <Grid>
                <StackLayout VerticalOptions="Center">
                    <Image Source="Beverage1.png"/>
                </StackLayout>
            </Grid>
        </radialMenu:SfRadialMenu.CenterButtonView>
        <radialMenu:SfRadialMenu.CenterButtonBackView>
            <Grid>
                <StackLayout VerticalOptions="Center">
                    <Image Source="Beverage2.png"/>
                </StackLayout>
            </Grid>
        </radialMenu:SfRadialMenu.CenterButtonBackView>
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            Grid centerButtonGrid = new Grid();
            Grid centerButtonBackGrid = new Grid();
            StackLayout centerButtonLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Center
            };
            StackLayout centerButtonBackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Center
            };

            centerButtonLayout.Children.Add(new Image() { Source = "Beverage1.png" });
            centerButtonGrid.Children.Add(centerButtonLayout);
            centerButtonBackLayout.Children.Add(new Image() { Source = "Beverage2.png" });
            centerButtonBackGrid.Children.Add(centerButtonBackLayout);

            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                CenterButtonView = centerButtonGrid,
                CenterButtonBackView = centerButtonBackGrid
            };
        }
    }
}

{% endhighlight %}

{% endtabs %}

## EnableCenterButtonAnimation

The [`EnableCenterButtonAnimation`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_EnableCenterButtonAnimationProperty) is used to either enable or disable animation of the center button in [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu  EnableCenterButtonAnimation="True">
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Bold" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Copy" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Undo" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Paste" FontSize="12"/>
            <radialMenu:SfRadialMenuItem Text="Color" FontSize="12"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu()
            {
                EnableCenterButtonAnimation = true
            };

            ObservableCollection<SfRadialMenuItem> itemCollection = new ObservableCollection<SfRadialMenuItem>();
            itemCollection.Add(new SfRadialMenuItem() { Text = "Bold", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Copy", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Paste", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Undo", FontSize = 12 });
            itemCollection.Add(new SfRadialMenuItem() { Text = "Color", FontSize = 12 });
            radialMenu.Items = itemCollection;
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Image for center button](images/centerButtonIconFont.png)
