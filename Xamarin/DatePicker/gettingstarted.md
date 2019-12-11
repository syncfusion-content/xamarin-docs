---
layout: post
title: Getting Started of Syncfusion DatePicker control for Xamarin.Forms
description: A quick tour to initial users for getting started with Syncfusion DatePicker control for Xamarin.Forms platform
platform: Xamarin
control: DatePicker
documentation: ug
---


# Getting Started

This section explains the steps required to configure a DatePicker control in a real-time scenario, and provides a walk-through on some of the customization features available in DatePicker control.

## Adding SfDatePicker reference

You can add SfDatePicker reference using one of the following methods:

**Method 1: Adding SfPicker reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfDatePicker to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfPicker](https://www.nuget.org/packages/Syncfusion.Xamarin.SfPicker), and then install it.

![Adding SfPicker reference from NuGet](images/Adding SfPicker reference.png)

N> Install the same version of SfPicker NuGet in all the projects.

**Method 2: Adding SfPicker reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfDatePicker control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfPicker assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfPicker.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfPicker.Android.dll<br/>Syncfusion.SfPicker.XForms.Android.dll<br/>Syncfusion.SfPicker.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfPicker.iOS.dll<br/>Syncfusion.SfPicker.XForms.iOS.dll<br/>Syncfusion.SfPicker.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfInput.UWP.dll<br/>Syncfusion.SfShared.UWP.dll<br/>Syncfusion.SfPicker.XForms.UWP.dll<br/>Syncfusion.SfPicker.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To learn more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Initialize DatePicker on each platform

To use DatePicker in Xamarin application, each platform project must initialize the DatePicker renderer. These initializing steps vary from platform to platform, and it is discussed in the following sections.

### Android

The Android launches the DatePicker without any initialization, and it is enough to only initialize the Xamarin.Forms Framework to launch the application.

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch the DatePicker in iOS, call the `SfDatePickerRenderer.Init()` in the FinishedLaunching overridden method of the `AppDelegate` class after the Xamarin.Forms Framework has been initialized and before the LoadApplication is called as demonstrated in the following code example.

{% highlight c# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

…

global::Xamarin.Forms.Forms.Init ();

SfDatePickerRenderer.Init();

LoadApplication (new App ());

…

}
{% endhighlight %}

### Universal Windows Platform (UWP)

To launch the DatePicker in UWP, call the `SfDatePickerRenderer.Init()` in the `MainPage` constructor before the `LoadApplication` is called as demonstrated in the following code example.

{% highlight c# %}

public MainPage()

{

…

SfDatePickerRenderer.Init();

LoadApplication (new App ());

…

}
{% endhighlight %}

### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed application is in Release Mode.

The above issues can be resolved by initializing the picker assemblies in `App.xaml.cs` in UWP project as shown in the following code snippet.

{% highlight c# %}
//In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)

{

…

rootFrame.NavigationFailed += OnNavigationFailed;



//You will need to add `using System.Reflection;`

List<Assembly> assembliesToInclude = new List<Assembly>();

//Now, add all the assemblies your app uses

assembliesToInclude.Add(typeof(SfDatePickerRenderer).GetTypeInfo().Assembly);

//Replaces Xamarin.Forms.Forms.Init(e);        

Xamarin.Forms.Forms.Init(e, assembliesToInclude);



…     

}
{% endhighlight %}

### Create a simple DatePicker

This section explains how to create a simple DatePicker control and configure it. DatePicker can be configured by using XAML or C# code. 

### Create a Xamarin.Forms project 

Create a new blank project (Xamarin.Forms portable) by using Visual Studio or Xamarin Studio for Xamarin.Forms. 

### Adding picker in Xamarin.Forms project

1. Add the required assembly reference in PCL, and other renderer projects as discussed in **Adding** **DatePicker** **reference** section.
2. Add DatePicker control's two way XAML or C#.
* XAML Page
  * Set SfDatePicker control namespace as ` xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"` in XAML Content page.
  * Set the SfDatePicker control in content property of contentPage.
* C# Page
  * Import SfDatePicker control namespace as `using Syncfusion.SfPicker.XForms;` in C# ContentPage.
  * Create a new SfDatePicker instance in ContentPage constructor, and assign SfDatePicker instance to ContentPage content property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker();
            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Set header to the DatePicker

The SfDatePicker control allows you to the define header text by setting the `SfDatePicker.HeaderText`, and enable SfPicker header by setting `SfDatePicker.ShowHeader` property to true. The default value of `SfDatePicker.ShowHeader` is "true".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker HeaderText="Select a date"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                HeaderText = "Select a date"
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Enable validation button in footer

In SfDatePicker control, validation buttons (OK and Cancel)can be enabled by setting `SfDatePicker.ShowFooter` property to true. The default value of `SfDatePicker.ShowFooter` property is "false".

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker ShowFooter="True"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}  

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                ShowFooter = true
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### PickerHeight and PickerWidth

The SfDatePicker control allows you to the change the height and the width of the picker using the `SfDatePicker.PickerHeight`, and `SfDatePicker.PickerWidth` properties.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <Grid>
            <syncfusion:SfDatePicker x:Name="datepicker"
                                     PickerMode="Dialog"
                                     PickerHeight="300"
                                     PickerWidth="300"/> >
            <Button Text="Open Picker" 
                    x:Name="pickerButton"
                    Clicked="Button_Clicked"
                    HorizontalOptions="Center"
                    VerticalOptions="Center"
                    HeightRequest="50" 
                    WidthRequest="100"/>
        </Grid>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using System;
using System.ComponentModel;
using System.Runtime.CompilerServices;
using System.Windows.Input;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        SfDatePicker datePicker;
        public MainPage()
        {
            InitializeComponent();
            Grid grid = new Grid();
            datePicker = new SfDatePicker()
            {
                PickerMode = DatePickerMode.Dialog,
                PickerHeight = 300,
                PickerWidth = 300
            };

            Button pickerButton = new Button()
            {
                Text = "Open Picker",
                HeightRequest = 50,
                WidthRequest = 100,
                HorizontalOptions = LayoutOptions.Center,
                VerticalOptions = LayoutOptions.Center
            };

            pickerButton.Clicked += Button_Clicked;

            grid.Children.Add(datePicker);
            grid.Children.Add(pickerButton);
            this.Content = grid;
        }

        private void Button_Clicked(object sender, System.EventArgs e)
        {
            datePicker.IsOpen = true;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Date

The date can be selected by using the Date property. The default value of Date is current date.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:DatePickerSample"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Pickers;assembly=Syncfusion.SfPicker.XForms"
             x:Class="DatePickerSample.MainPage">
    <ContentPage.Content>
        <syncfusion:SfDatePicker x:Name="datepicker"
                                 Date="3/5/2011"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.Pickers;
using Xamarin.Forms;

namespace DatePickerSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfDatePicker datePicker = new SfDatePicker()
            {
                Date = new System.DateTime(2011, 3, 5)
            };

            this.Content = datePicker;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![OverView of SfDatePicker](images/GettingStatrted_DatePicker.png)

We have attached sample for reference. You can download the sample from the following link.

Sample link:[GettingStarted](https://www.syncfusion.com/downloads/support/directtrac/general/ze/DatePickerSample-472749877)