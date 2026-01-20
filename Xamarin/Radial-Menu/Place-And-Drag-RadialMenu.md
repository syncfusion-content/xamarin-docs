---
layout: post
title: Placing and Dragging RadialMenu in Xamarin Radial Menu | Syncfusion
description: Learn about placing and dragging RadialMenu support in the Syncfusion Xamarin Radial Menu (SfRadialMenu) control and more.
platform: Xamarin
control: SfRadialMenu
documentation: ug
---

# Placing and Dragging RadialMenu in Xamarin Radial Menu (SfRadialMenu)

You can place the radial menu anywhere on its parent layout and drag it within the parent layout.

## Dragging RadialMenu

You can enable or disable dragging by using the [`IsDragEnabled`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_IsDragEnabled) property.

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
            <OnPlatform x:TypeArguments="x:String" x:Key="customfontfamily" iOS="Segoe MDL2 Assets" Android="radialmenu_Segoe MDL2 Assets.ttf" WinPhone="radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"  />
        </ResourceDictionary>
    </ContentPage.Resources>
    <ContentPage.Content>
        <radialMenu:SfRadialMenu x:Name="radialMenu" 
                                 IsDragEnabled="true" 
                                 CenterButtonText="&#xe713;"
                                 CenterButtonFontFamily="{StaticResource customfontfamily}" 
                                 CenterButtonRadius="30"
                                 CenterButtonFontSize="26" 
                                 CenterButtonTextColor="White"
                                 CenterButtonBorderColor="White" 
                                 CenterButtonBorderThickness="3">
        </radialMenu:SfRadialMenu>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

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
                IsDragEnabled = true,
                CenterButtonText = "\uE713",
                CenterButtonFontFamily = Device.RuntimePlatform == "iOS" ? "Segoe MDL2 Assets" : Device.RuntimePlatform == "Android" ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonRadius = 30,
                CenterButtonFontSize = 26,
                CenterButtonTextColor = Color.White,
                CenterButtonBorderColor = Color.White,
                CenterButtonBorderThickness = 3
            };
            this.Content = radialMenu;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Image for dragging](images/dragging.png)

## Drag Events

[`SfRadialMenu`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html) provides events for [`DragBegin`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_DragBegin) and [`DragEnd`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_DragEnd), which are triggered when the RadialMenu is dragged.

### DragBegin Event

This event is triggered when the RadialMenu begins to drag, utilizing the [`DragBeginEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.DragBeginEventArgs.html).

- [`Position`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.DragBeginEventArgs.html#Syncfusion_SfRadialMenu_XForms_DragBeginEventArgs_Position): Gets the start position of the RadialMenu.
- [`Handled`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.DragBeginEventArgs.html#Syncfusion_SfRadialMenu_XForms_DragBeginEventArgs_Handled): Gets and sets a boolean value for enabling and disabling the dragging of the RadialMenu.

To hook the [`DragBegin`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_DragBegin) event and get the start position while restricting dragging, refer to the following code example:

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
            <OnPlatform x:TypeArguments="x:String" x:Key="customfontfamily" iOS="Segoe MDL2 Assets" Android="radialmenu_Segoe MDL2 Assets.ttf" WinPhone="radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"  />
        </ResourceDictionary>
    </ContentPage.Resources>
    <radialMenu:SfRadialMenu x:Name="radialMenu" 
                             IsDragEnabled="true" 
                             DragBegin="RadialMenu_DragBegin"
                             CenterButtonText="&#xe713;"
                             CenterButtonFontFamily="{StaticResource customfontfamily}" 
                             CenterButtonRadius="30"
                             CenterButtonFontSize="26" 
                             CenterButtonTextColor="White"
                             CenterButtonBorderColor="White" 
                             CenterButtonBorderThickness="3">
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

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
                IsDragEnabled = true,
                CenterButtonText = "\uE713",
                CenterButtonFontFamily = Device.RuntimePlatform == "iOS" ? "Segoe MDL2 Assets" : Device.RuntimePlatform == "Android" ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonRadius = 30,
                CenterButtonFontSize = 26,
                CenterButtonTextColor = Color.White,
                CenterButtonBorderColor = Color.White,
                CenterButtonBorderThickness = 3
            };

            radialMenu.DragBegin += RadialMenu_DragBegin;
            this.Content = radialMenu;
        }

        private void RadialMenu_DragBegin(object sender, DragBeginEventArgs e)
        {
            e.Handled = true;
        }
    }
}

{% endhighlight %}
{% endtabs %}

### DragEnd Event

This event is triggered when dragging ends in the RadialMenu, using [`DragEndEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.DragEndEventArgs.html).

- [`OldValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.DragEndEventArgs.html#Syncfusion_SfRadialMenu_XForms_DragEndEventArgs_OldValue): Gets the start position of the RadialMenu.
- [`NewValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.DragEndEventArgs.html#Syncfusion_SfRadialMenu_XForms_DragEndEventArgs_NewValue): Gets the end position of the RadialMenu.
- [`Handled`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.DragEndEventArgs.html#Syncfusion_SfRadialMenu_XForms_DragEndEventArgs_Handled): Gets and sets a boolean value for restricting the RadialMenu from moving to another position.

To hook the [`DragEnd`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRadialMenu.XForms.SfRadialMenu.html#Syncfusion_SfRadialMenu_XForms_SfRadialMenu_DragEnd) event and determine the start and end positions, while restricting the movement of the RadialMenu, refer to the following code example:

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
            <OnPlatform x:TypeArguments="x:String" x:Key="customfontfamily" iOS="Segoe MDL2 Assets" Android="radialmenu_Segoe MDL2 Assets.ttf" WinPhone="radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"  />
        </ResourceDictionary>
    </ContentPage.Resources>
    <radialMenu:SfRadialMenu x:Name="radialMenu" 
                             IsDragEnabled="true" 
                             DragEnd="radialMenu_DragEnd"
                             CenterButtonText="&#xe713;"
                             CenterButtonFontFamily="{StaticResource customfontfamily}" 
                             CenterButtonRadius="30"
                             CenterButtonFontSize="26" 
                             CenterButtonTextColor="White"
                             CenterButtonBorderColor="White" 
                             CenterButtonBorderThickness="3">
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

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
                IsDragEnabled = true,
                CenterButtonText = "\uE713",
                CenterButtonFontFamily = Device.RuntimePlatform == "iOS" ? "Segoe MDL2 Assets" : Device.RuntimePlatform == "Android" ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonRadius = 30,
                CenterButtonFontSize = 26,
                CenterButtonTextColor = Color.White,
                CenterButtonBorderColor = Color.White,
                CenterButtonBorderThickness = 3
            };

            radialMenu.DragEnd += radialMenu_DragEnd;
            this.Content = radialMenu;
        }

        private void radialMenu_DragEnd(object sender, DragEndEventArgs e)
        {
            e.Handled = true;
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Placing RadialMenu

You can position the radial menu anywhere on its parent layout. The radial menu's position is calculated based on the parent layout's center point.

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
            <OnPlatform x:TypeArguments="x:String" x:Key="customfontfamily" iOS="Segoe MDL2 Assets" Android="radialmenu_Segoe MDL2 Assets.ttf" WinPhone="radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets"  />
        </ResourceDictionary>
    </ContentPage.Resources>
    <radialMenu:SfRadialMenu x:Name="radialMenu" 
                             Point="100, 150"
                             CenterButtonText="&#xe713;"
                             CenterButtonFontFamily="{StaticResource customfontfamily}" 
                             CenterButtonRadius="30"
                             CenterButtonFontSize="26" 
                             CenterButtonTextColor="White"
                             CenterButtonBorderColor="White" 
                             CenterButtonBorderThickness="3">
    </radialMenu:SfRadialMenu>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

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
                CenterButtonText = "\uE713",
                CenterButtonFontFamily = Device.RuntimePlatform == "iOS" ? "Segoe MDL2 Assets" : Device.RuntimePlatform == "Android" ? "radialmenu_Segoe MDL2 Assets.ttf" : "radialmenu_Segoe_MDL2_Assets.ttf#Segoe MDL2 Assets",
                CenterButtonRadius = 30,
                CenterButtonFontSize = 26,
                CenterButtonTextColor = Color.White,
                CenterButtonBorderColor = Color.White,
                CenterButtonBorderThickness = 3,
                Point = new Point(100, 150)
            };

            this.Content = radialMenu;
        }
    }
}
            
{% endhighlight %}
{% endtabs %}

![Image for position](images/position.png)
