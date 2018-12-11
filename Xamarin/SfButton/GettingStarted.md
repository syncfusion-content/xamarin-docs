---
layout: post
title: Getting Started for Syncfusion Essential Xamarin.Forms SfButton
description: How to create a simple button view, add caption, background image, icon, enable toggle view and customize visual states.
platform: xamarin.forms
control: sfbutton
documentation: ug
---

# Getting Started

This section explains the steps required to work with the button control for Xamarin.Forms.

## Adding button reference

Syncfusion components for Xamarin.Forms are available in [nuget.org](https://www.nuget.org/). To add the button control to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Buttons](https://www.nuget.org/packages/Syncfusion.Xamarin.Buttons), and then install it.

![SfButton Nuget installation](images/nuget.png)

To learn more about obtaining Syncfusion components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac#) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows#). If you prefer to manually reference the assemblies instead of NuGet, refer to this [documentation](https://help.syncfusion.com/xamarin/introduction/control-dependencies#button) to know about the dependent assemblies for button.

N> Install the same version of the button NuGet in all the projects.

After adding the assembly reference, an additional step is required for iOS and UWP projects.

### Additional step for iOS

To launch `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html) in iOS, call `SfButtonRenderer.Init()` in the `FinishedLaunching` overridden method of the `AppDelegate` class in iOS Project as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    LoadApplication(new App());
    SfButtonRenderer.Init();
    return base.FinishedLaunching(app, options);
}
{% endhighlight %}
{% endtabs %}

### Additional step for UWP

This step is required only if the application is deployed in Release mode with .NET native tool chain enabled. It is needed for resolving the known Framework issue “Custom controls not rendering in Release mode” in UWP platform. Initializing the `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html) assembly at the `OnLaunched` overridden method of the `App` class in UWP project is the suggested work around. The following code example demonstrates initializing the `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html) assembly.

{% tabs %}
{% highlight c# %}
protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    ..... 
    rootFrame.NavigationFailed += OnNavigationFailed;
    // Add `using System.Reflection;` 
    List<Assembly> assembliesToInclude = new List<Assembly>();
    //Now, add all the assemblies that your app uses 
    assembliesToInclude.Add(typeof(SfButtonRenderer).GetTypeInfo().Assembly);
    // replaces Xamarin.Forms.Forms.Init(e);
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
    ..... 
}
{% endhighlight %}
{% endtabs %}

## Creating a simple SfButton

The `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html) control is configured entirely in C# code or in XAML markup. The following steps explain how to create a `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html) and configure its elements.

### Adding namespace for referred assemblies

{% tabs %}
{% highlight xaml %}
xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Buttons;
{% endhighlight %}
{% endtabs %}

### Referring SfButton control with declared suffix name for namespace

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:SfButton"
             xmlns:buttons="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
             x:Class="SfButton.MainPage">

    <StackLayout HorizontalOptions="Center" VerticalOptions="Center">
        <buttons:SfButton x:Name="SfButton"/>
    </StackLayout>

</ContentPage>

{% endhighlight %}
{% highlight c# %}
namespace SfButton
{
    using Syncfusion.XForms.Buttons;
    using Xamarin.Forms;

    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            stackLayout.HorizontalOptions = LayoutOptions.Center;
            stackLayout.VerticalOptions = LayoutOptions.Center;
            SfButton button = new SfButton();
            stackLayout.Children.Add(button);
            this.Content = stackLayout;
        }
    }
}
{% endhighlight %}
{% endtabs %}

## Setting caption

The button caption can be defined using the `Text`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~Text.html) property of `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html). This caption normally describes the meaning of the button and is displayed in button.

{% tabs %}
{% highlight xaml %}

<buttons:SfButton x:Name="SfButton" Text="Button"/>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";

{% endhighlight %}
{% endtabs %}

![SfButton with caption](images/ButtonWithText.jpg)

## Toggle button

The button behavior can be changed as toggle button by defining the `IsCheckable`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~IsCheckable.html) property of `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html).

{% tabs %}
{% highlight xaml %}

<buttons:SfButton x:Name="SfButton" Text="Button" IsCheckable="True"/>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.IsCheckable = true;

{% endhighlight %}
{% endtabs %}

Checked state:

![SfButton with toggle pressed state](images/Toggle_Pressed_State.jpg)

Unchecked state:

![SfButton with toggle relased state](images/Toggle_Released_Button.jpg)

## Button icon

The button icon can be defined using the `ImageSource`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ImageSource.html) and `ShowIcon`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~ShowIcon.html) properties of `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html).

{% tabs %}
{% highlight xaml %}

<buttons:SfButton x:Name="SfButton" Text="Button" ShowIcon="True" ImageSource="button_Heart.png"/>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.ImageSource = "button_Heart.png";
button.ShowIcon = true;

{% endhighlight %}
{% endtabs %}

![SfButton with button icon](images/ButtonWithIcon.jpg)

## Button background image

The button background icon can be defined using the `BackgroundImage`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton~BackgroundImage.html) property of `SfButton`(https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html).

{% tabs %}
{% highlight xaml %}

<buttons:SfButton x:Name="SfButton" Text="Button" BackgroundImage="button_background.png" CornerRadius="20" WidthRequest="100"/>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";
button.WidthRequest = 100;
button.BackgroundImage = "button_background.png";
button.CornerRadius = new Thickness(20);

{% endhighlight %}
{% endtabs %}

![Button with background image](images/ButtonWithBackgroundImage.jpg)