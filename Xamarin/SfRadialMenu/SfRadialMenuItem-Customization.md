---
layout: post
title: Syncfusion RadialMenu item customization in Xamarin.Forms
description: Working with various options available in SfRadialMenuItems in Xamarin.Forms
platform: Xamarin
control: SfRadialMenu
documentation: ug
---

# SfRadialMenuItem Customization

The `SfRadialMenuItem` class provides various options to customize the items by giving `Custom Views`, `FontIcons`, and `Images`. You can add radial menu items by hierarchy. To add a SfRadialMenuItem with SfRadialMenu, create an instance of SfRadialMenuItem, and add it to the `Items` property, which is available in SfRadialMenu.

## Items

The [`Items`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~ItemsProperty.html) property populates the items to the inner rim of [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) when tapping the items of outer rim.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Copy">
                <radialMenu:SfRadialMenuItem.Items>
                    <radialMenu:SfRadialMenuItem Text="Paste"/>
                </radialMenu:SfRadialMenuItem.Items>
            </radialMenu:SfRadialMenuItem>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Copy" });
            radialMenu.Items[0].Items.Add(new SfRadialMenuItem() { Text = "Paste" });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Text

The [`Text`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~TextProperty.html) property provides text to the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Cut"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem() { Text = "Copy" });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## ItemHeight

The [`ItemHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~ItemHeightProperty.html) changes the height of the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Cut"
                                         ItemHeight="10"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                Text = "Cut",
                ItemHeight = 10
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## ItemWidth

The [`ItemWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~ItemWidthProperty.html) property changes the width of the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Cut"
                                         ItemWidth="10"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                Text = "Cut",
                ItemWidth = 10
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## BackgroundColor

The [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~BackgroundColorProperty.html) property changes the background color of the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Cut"
                                         BackgroundColor="Pink"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                Text = "Cut",
                BackgroundColor = Color.Pink
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## FontFamily

The [`FontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~FontFamilyProperty.html) property changes the font family of text in [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Cut"
                                        FontFamily="Times New Roman"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                Text = "Cut",
                FontFamily = "Times New Roman"
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## FontSize

The [`FontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~FontSizeProperty.html) property changes the text size in the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Cut"
                                        FontSize="20"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>

    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                Text = "Cut",
                FontSize = 20
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## FontAttribute

The [`FontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~FontAttributesProperty.html) property changes the font attributes of text in [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Text="Cut"
                                        FontAttributes="Bold"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                Text = "Cut",
                FontAttributes = FontAttributes.Bold
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Image

The [`Image`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~ImageProperty.html) property provides image to the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem Image="user.png"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                Image = "user.png"
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## VisibleSegmentCount

The [`VisibleSegmentsCount`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~VisibleSegmentsCountProperty.html) property provides the number of items to be displayed in radial menu.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem VisibleSegmentsCount="3"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
               VisibleSegmentsCount = 3
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## BackgroundImage

The [`BackgroundImage`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~BackgroundImageProperty.html) property provides the background image to the [`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem BackgroundImage="facebook.png"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                BackgroundImage = "facebook.png"
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

You can download the sample for reference from the following link: [Sample for adding BackgroundImage](http://www.syncfusion.com/downloads/support/directtrac/general/ze/sample550939797.zip).

## FontIconText

The [`FontIconText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~FontIconTextProperty.html) property provides font icon to the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem FontIconText="&#xe734;"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                FontIconText = "\uE734"
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## IconFontColor

The [`IconFontColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~IconFontColorProperty.html) property changes the color of font icon in [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem FontIconText="&#xe734;"
                                         IconFontColor="#313131"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                FontIconText = "\uE734",
                IconFontColor = Color.FromHex("#313131")
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## IconFontSize

The [`IconFontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~IconFontSizeProperty.html) property changes the size of font icon in the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem FontIconText="&#xe734;"
                                         IconFontColor="#313131"
                                         IconFontSize="10"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                FontIconText = "\uE734",
                IconFontColor = Color.FromHex("#313131"),
                IconFontSize = 10
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## IconFontFamily

The [`IconFontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~IconFontFamilyProperty.html) property changes the font family of font icon in the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

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
    <ContentPage.Content>
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem FontIconText="&#xe734;"
                                         IconFontColor="#313131"
                                         IconFontSize="10"
                                         IconFontFamily="{StaticResource customfontfamily}"/>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
    </ContentPage.Content>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                FontIconText = "\uE734",
                IconFontColor = Color.FromHex("#313131"),
                IconFontSize = 10,
                IconFontFamily = Device.RuntimePlatform == Device.iOS ? "Segoe MDL2 Assets" : Device.RuntimePlatform == Device.Android ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"
            });
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

N> https://xamarinhelp.com/custom-fonts-xamarin-forms/ provides how to add the ttf file in each platform

## View

The [`View`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem~ViewProperty.html) provides custom view to the [`SfRadialMenuItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms~Syncfusion.SfRadialMenu.XForms.SfRadialMenuItem.html).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:RadialSample"
             xmlns:radialMenu="clr-namespace:Syncfusion.SfRadialMenu.XForms;assembly=Syncfusion.SfRadialMenu.XForms"
             x:Class="RadialSample.MainPage">
    <radialMenu:SfRadialMenu>
        <radialMenu:SfRadialMenu.Items>
            <radialMenu:SfRadialMenuItem>
                <radialMenu:SfRadialMenuItem.View>
                    <Label Text="Cut"
                               HorizontalTextAlignment="Center"
                               VerticalTextAlignment="Center"/>
                </radialMenu:SfRadialMenuItem.View>
            </radialMenu:SfRadialMenuItem>
        </radialMenu:SfRadialMenu.Items>
    </radialMenu:SfRadialMenu>
</ContentPage>
    
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfRadialMenu.XForms;
using Xamarin.Forms;

namespace RadialSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfRadialMenu radialMenu = new SfRadialMenu();
            radialMenu.Items.Add(new SfRadialMenuItem()
            {
                View = new Label()
                {
                    Text = "Cut",
                    HorizontalTextAlignment = TextAlignment.Center,
                    VerticalTextAlignment = TextAlignment.Center
                }
            });

            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}