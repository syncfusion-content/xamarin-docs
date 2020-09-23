---
layout: post
title: Getting Started for Syncfusion Essential Xamarin.Forms SfButton
description: How to create a simple button view, add caption, background image, icon, enable toggle view and customize visual states.
platform: xamarin.forms
control: sfbutton
documentation: ug
---

# Getting Started with Xamarin Button (SfButton)

This section explains the steps required to work with the button control for Xamarin.Forms.

## Adding SfButton reference

You can add SfButton reference using one of the following methods:

**Method 1: Adding SfButton reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfButton to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Buttons](https://www.nuget.org/packages/Syncfusion.Xamarin.Buttons), and then install it.

![Adding SfButton reference from NuGet](Images/Adding SfButton reference.png)

N> 
* Install the same version of SfButton NuGet in all the projects.
* In addition, you need to install the [Syncfusion.Xamarin.Buttons.WPF]() package for Xamarin.Forms WPF platform only.

**Method 2: Adding SfButton reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfButton control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfButton assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.Android.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.iOS.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.UWP.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
tr>
<td>WPF</td>
<td>Syncfusion.Buttons.XForms.dll<br/>Syncfusion.Buttons.XForms.WPF.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.WPF.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

N> After adding the reference, an additional step is required for iOS and UWP projects. If you are adding the references from toolbox, this step is not needed.

### Additional step for iOS

To launch [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) in iOS, call `SfButtonRenderer.Init()` in the `FinishedLaunching` overridden method of the `AppDelegate` class in iOS Project as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    LoadApplication(new App());
    Syncfusion.XForms.iOS.Border.SfBorderRenderer.Init();
    Syncfusion.XForms.iOS.Buttons.SfButtonRenderer.Init();
    return base.FinishedLaunching(app, options);
}
{% endhighlight %}
{% endtabs %}

### Additional step for UWP

This step is required only if the application is deployed in Release mode with .NET native tool chain enabled. It is needed for resolving the known Framework issue “Custom controls not rendering in Release mode” in UWP platform. Initializing the [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) assembly at the `OnLaunched` overridden method of the `App` class in UWP project is the suggested work around. The following code example demonstrates initializing the [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) assembly.

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
    assembliesToInclude.Add(typeof(SfBorderRenderer).GetTypeInfo().Assembly);
    // replaces Xamarin.Forms.Forms.Init(e);
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
    ..... 
}
{% endhighlight %}
{% endtabs %}

### Additional step for WPF

To launch the button in WPF, call the SfButtonRenderer.Init() method in the MainWindow constructor of the MainWindow class after the Xamarin.Forms framework has been initialized and before the LoadApplication method is called as demonstrated in the following code sample.

{% tabs %}
{% highlight C# %} 

public partial class MainWindow : FormsApplicationPage
{
     public MainWindow()
     { 
            InitializeComponent();

            Forms.Init();
            
            Syncfusion.XForms.WPF.Border.SfBorderRenderer.Init();
            
            Syncfusion.XForms.WPF.Buttons.SfButtonRenderer.Init();
            
            LoadApplication(new App());
     }
}

{% endhighlight %}
{% endtabs %}

## Creating a simple SfButton

The [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) control is configured entirely in C# code or in XAML markup. The following steps explain how to create a [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) and configure its elements.

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

The button caption can be defined using the [`Text`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_Text) property of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html). This caption normally describes the meaning of the button and is displayed in button.

{% tabs %}
{% highlight xaml %}

<buttons:SfButton x:Name="SfButton" Text="Button"/>

{% endhighlight %}
{% highlight c# %}

SfButton button = new SfButton();
button.Text = "Button";

{% endhighlight %}
{% endtabs %}

![SfButton with caption](images/ButtonWithText.png)

## Toggle button

The button behavior can be changed as toggle button by defining the [`IsCheckable`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_IsCheckable) property of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

![SfButton with toggle pressed state](images/Toggle_Pressed_State.png)

Unchecked state:

![SfButton with toggle relased state](images/Toggle_Released_Button.png)

## Button icon

The button icon can be defined using the [`ImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ImageSource) and [`ShowIcon`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_ShowIcon) properties of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

![SfButton with button icon](images/ButtonWithIcon.png)

## Button background image

The button background icon can be defined using the [`BackgroundImage`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html#Syncfusion_XForms_Buttons_SfButton_BackgroundImage) property of [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html).

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

![Button with background image](images/ButtonWithBackgroundImage.png)

## See also

[How to create Xamarin.Forms image button](https://www.syncfusion.com/kb/10808/how-to-create-xamarin-forms-image-button)

[How to disable Xamarin.Forms button](https://www.syncfusion.com/kb/11036/how-to-disable-xamarin-forms-button)