---
layout: post
title: Getting Started of Syncfusion Picker control for Xamarin.Forms
description: Getting Started of Picker control
platform: Xamarin
control: Picker
documentation: ug
---


# Getting Started

This section explains the steps required to configure a picker control in a real-time scenario, and provides a walk-through on some of the customization features available in picker control.

## Adding Picker reference

Refer to this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation# "") to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfpicker "") to know about the assemblies required for adding picker control to your project.

## Initialize picker on each platform

To use picker in Xamarin application, each platform project must initialize the picker renderer. These initializing steps vary from platform to platform, and it is discussed in the following sections.

### Android

The Android launches the picker without any initialization, and it is enough to only initialize the Xamarin.Forms Framework to launch the application.

### iOS

To launch the picker in iOS, call the `SfPickerRenderer.Init()` in the FinishedLaunching overridden method of the `AppDelegate` class after the Xamarin.Forms Framework has been initialized and before the LoadApplication is called as demonstrated in the following code example.

{% highlight c# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

…

global::Xamarin.Forms.Forms.Init ();

SfPickerRenderer.Init();

LoadApplication (new App ());

…

}
{% endhighlight %}

### Universal Windows Platform (UWP)

To launch the picker in UWP, call the `SfPickerRenderer.Init()` in the `MainPage` constructor before the `LoadApplication` is called as demonstrated in the following code example.

{% highlight c# %}

public MainPage()

{

…

SfPickerRenderer.Init();

LoadApplication (new App ());

…

}
{% endhighlight %}

### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed application is in Release Mode.

The above issues can be resolved by initializing the picker assemblies in `App.xaml.cs` in UWP project as shown in the following code snippet.

{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)

{

…

rootFrame.NavigationFailed += OnNavigationFailed;



// you'll need to add `using System.Reflection;`

List<Assembly> assembliesToInclude = new List<Assembly>();

//Now, add all the assemblies your app uses

assembliesToInclude.Add(typeof(SfPickerRenderer).GetTypeInfo().Assembly);

// replaces Xamarin.Forms.Forms.Init(e);        

Xamarin.Forms.Forms.Init(e, assembliesToInclude);



…     

}
{% endhighlight %}

### Create a simple picker

This section explains how to create a simple picker control and configure it. picker can be configured by using XAML or C# code. 

### Create a Xamarin.Forms project 

Create a new blank project (Xamarin.Forms portable) by using Visual Studio or Xamarin Studio for Xamarin.Forms. 

### Adding picker in Xamarin.Forms project

1. Add the required assembly reference in PCL, and other renderer projects as discussed in **Adding** **picker** **reference** section.
2. Add picker control's two way XAML or C#.
* XAML Page
  * Set SfPicker control namespace as `xmlns:syncfusion="clr- namespace:Syncfusion.SfPicker.XForms;assembly=Syncfusion.SfPicker.XForms”` in XAML Content page.
  * Set the SfPicker control in content property of contentPage.
* C# Page
  * Import SfPicker control namespace as `using Syncfusion.SfPicker.XForms;` in C# ContentPage.
  * Create a new SfPicker instance in ContentPage constructor, and assign SfPicker instance to ContentPage content property.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:syncfusion="clr-namespace:Syncfusion.SfPicker.XForms;assembly=Syncfusion.SfPicker.XForms"

xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

x:Class="GettingStarted.PickerSample">

<ContentPage.Content>

<syncfusion:SfPicker x:Name="picker" />

</ContentPage.Content>

</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfPicker.XForms;

using Xamarin.Forms;

using Xamarin.Forms.Xaml;

namespace GettingStarted

{

[XamlCompilation(XamlCompilationOptions.Compile)]

public partial class PickerSample : ContentPage

{

SfPicker picker;

public PickerSample()

{

InitializeComponent();

picker = new SfPicker();

this.Content = picker;

}

}

}

{% endhighlight %}
{% endtabs %}

### Set header to the picker

The picker control allows you to the define header text by setting the `SfPicker.HeaderText`, and enable SfPicker header by setting `SfPicker.ShowHeader` property to true. Default value of `SfPicker.ShowHeader` is true.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker x:Name="picker" HeaderText="Select a Color" />

{% endhighlight %}

{% highlight c# %}

picker.HeaderText = "Select a Color";

{% endhighlight %}
{% endtabs %}

### Adding picker items 

picker control is a data bounded control. Hence, you must create collection of data’s and bind it to picker control.

* Create a simple Observable Collection with string type of data for the picker 

{% highlight c# %}

public class ColorInfo

{

private ObservableCollection<string> _color;

public ObservableCollection<string> Colors

{

get { return _color; }

set { _color = value; }

}

public ColorInfo()

{

Colors = new ObservableCollection<string>();

Colors.Add("Red");

Colors.Add("Green");

Colors.Add("Yellow");

Colors.Add("Blue");

Colors.Add("SkyBlue");

Colors.Add("Orange");

Colors.Add("Gray");

Colors.Add("Pink");

}

}
{% endhighlight %}

* Bind the Collection to picker

picker control allows you to bind collection of data by setting the `SfPicker.ItemsSource` property. You can bind the collection of data in both XAML or C#.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>

<ContentPage

x:Class="GettingStarted.PickerSample"

xmlns="http://xamarin.com/schemas/2014/forms"

xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

xmlns:local="clr-namespace:GettingStarted"

xmlns:syncfusion="clr-namespace:Syncfusion.SfPicker.XForms;assembly=Syncfusion.SfPicker.XForms">

<ContentPage.BindingContext>

<local:ColorInfo />

</ContentPage.BindingContext>

<ContentPage.Content>

<syncfusion:SfPicker

x:Name="picker"

HeaderText="Select a Color"

ItemsSource="{Binding Colors}" />

</ContentPage.Content>

</ContentPage>

{% endhighlight %}

{% highlight c# %}

ColorInfo info = new ColorInfo();

picker.ItemsSource = info.Colors;

{% endhighlight %}
{% endtabs %}

### Set title to the items 

picker control allows you to define title to the picker items by setting `SfPicker.ColumnHeaderText` and enable title of the picker items by setting `SfPicker.ShowColumnHeader` property to true. Default value of `SfPicker.ShowColumnHeader` is false.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="picker"

ColumnHeaderText="Color"

ShowColumnHeader="True" />

{% endhighlight %}

{% highlight c# %}

picker.ColumnHeaderText = "Color";

picker.ShowColumnHeader = true;

{% endhighlight %}
{% endtabs %}

### Enable validation button in footer

In picker control, validation buttons (OK and Cancel)can be enabled by setting `SfPicker.ShowFooter` property to true. Default value of `SfPicker.ShowFooter` property is false

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="picker"

ShowFooter="True" />

{% endhighlight %}

{% highlight c# %}  

picker.ShowFooter = true;

{% endhighlight %}
{% endtabs %}

### Open as dialog

 picker can be rendered as a dialog by setting the`SfPicker.PickerMode` property to Dialog. Default value of `SfPicker.PickerMode` property is Default. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker x:Name="picker" PickerMode="Dialog" />

{% endhighlight %}

{% highlight c# %}

picker.PickerMode = PickerMode.Dialog;

{% endhighlight %}
{% endtabs %}

The picker can be opened programmatically by setting  `SfPicker.IsOpen` property to true. Default value of `SfPicker.IsOpen` is false.

Note: This property is automatically changed to false when you close the dialog by click outside of dialog.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="picker"

IsOpen="True" 

PickerMode="Dialog" />

{% endhighlight %}

{% highlight c# %}

picker.IsOpen = true;

{% endhighlight %}
{% endtabs %}

The following screenshot illustrates the output of above code.

![Gettingstartedimage](images/forms_picker.png)

We have attached sample for reference. You can download the sample from the following link.

Sample link:[GettingStarted](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Picker_GettingStarted1412016889.zip)