---
layout: post
title: Getting Started with Xamarin.Forms AutoComplete | Syncfusion
description: A quick guide to help new users get started with the Syncfusion AutoComplete control for Xamarin.Forms applications
platform: xamarin
control: SfAutoComplete
documentation: ug
---

# Getting Started with Xamarin AutoComplete (SfAutoComplete)

This section explains how to create an AutoComplete control, populate it with data, and configure filtering options. This guide covers the essential features needed to get started with the AutoComplete control.

To get started quickly with the [Xamarin AutoComplete](https://www.syncfusion.com/xamarin-ui-controls/xamarin-autocomplete) (SfAutoComplete), you can watch this video tutorial:

<style>#XamarinAutoCompleteVideoTutorial{width : 90% !important; height: 400px !important }</style>
<iframe id='XamarinAutoCompleteVideoTutorial' src='https://www.youtube.com/embed/XT5-CKZCiH8'></iframe>

## Assembly deployment

After installing [Essential Studio for Xamarin](https://www.syncfusion.com/downloads/xamarin), you can find all the required assemblies in the installation folders, {Syncfusion Essential Studio Installed location}\Essential Studio\{Version #}\Xamarin\lib.

Example: C:\Program Files (x86)\Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib

> **Note:** On Mac, assemblies can be found in the unzipped package location (Documents/Syncfusion/{Version #}/Xamarin/lib).

## Adding SfAutoComplete reference

You can add the [`SfAutoComplete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html) reference using one of the following methods:

**Method 1: Adding SfAutoComplete reference from NuGet.org**

Syncfusion Xamarin components are available on [NuGet.org](https://www.nuget.org/). To add SfAutoComplete to your project, open the [NuGet package](https://help.syncfusion.com/xamarin/visual-studio-integration/nuget-packages) manager in Visual Studio, search for [Syncfusion.Xamarin.SfAutoComplete](https://www.nuget.org/packages/Syncfusion.Xamarin.SfAutoComplete), and install it.

![Adding SfAutoComplete reference](images/Getting-Started/Adding_SfAutoComplete_reference.png)

> **Note:** Install the same version of SfAutoComplete NuGet in all projects in your solution.

**Method 2: Adding SfAutoComplete reference from toolbox**

Syncfusion provides a Xamarin Toolbox. Using this toolbox, you can drag the [`SfAutoComplete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html) control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install the Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfAutoComplete assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead of using NuGet, add the following assemblies to the respective projects:

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfAutoComplete.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfAutoComplete.XForms.Android.dll<br/>Syncfusion.SfAutoComplete.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfAutoComplete.iOS.dll<br/>Syncfusion.SfAutoComplete.XForms.iOS.dll<br/>Syncfusion.SfAutoComplete.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfInput.UWP.dll<br/>Syncfusion.SfShared.UWP.dll<br/>Syncfusion.SfAutoComplete.XForms.UWP.dll<br/>Syncfusion.SfAutoComplete.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

> **Note:** To learn more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/installation/mac-installer/how-to-download) and [Windows](https://help.syncfusion.com/xamarin/installation/web-installer/how-to-download).

> **Important:** Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/overview) to learn about registering a Syncfusion license key in your Xamarin application to use our components.

### Additional Step for iOS

> **Note:** If you are adding the references from the toolbox, this step is not needed.

Create an instance of `SfAutoCompleteRenderer` in the `FinishedLaunching` overridden method of the AppDelegate class in your iOS project as shown below:

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
new Syncfusion.SfAutoComplete.XForms.iOS.SfAutoCompleteRenderer();

global::Xamarin.Forms.Forms.Init();

LoadApplication(new App());

return base.FinishedLaunching(app, options);
}	

{% endhighlight %}

{% endtabs %}

### Additional Step for UWP

This step is required only if the application is deployed in Release mode with .NET native tool chain enabled. It addresses the known Framework issue "Custom controls not rendering in Release mode" in UWP platform. Initialize the [`SfAutoComplete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html) assembly in the `OnLaunched` overridden method of the App class in your UWP project as shown below:

{% tabs %}

{% highlight C# %}

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
#if DEBUG
if (System.Diagnostics.Debugger.IsAttached)
{
	this.DebugSettings.EnableFrameRateCounter = true;
}
#endif

Frame rootFrame = Window.Current.Content as Frame; 
if (rootFrame == null)
{
	rootFrame = new Frame();
	rootFrame.NavigationFailed += OnNavigationFailed;                
	List<System.Reflection.Assembly> assembliesToInclude = new List<System.Reflection.Assembly>();
	// Add all the renderer assemblies your app uses 
	assembliesToInclude.Add(typeof(Syncfusion.SfAutoComplete.XForms.UWP.SfAutoCompleteRenderer).GetTypeInfo().Assembly);
	// Replace the Xamarin.Forms.Forms.Init(e);        
	Xamarin.Forms.Forms.Init(e, assembliesToInclude);
	if (e.PreviousExecutionState == ApplicationExecutionState.Terminated)
	{
		//TODO: Load state from previously suspended application
	}
	// Place the frame in the current Window
	Window.Current.Content = rootFrame;
}
if (rootFrame.Content == null)
{
	// When the navigation stack isn't restored navigate to the first page,
	// configuring the new page by passing required information as a navigation
	// parameter
	rootFrame.Navigate(typeof(MainPage), e.Arguments);
}
// Ensure the current window is active
Window.Current.Activate();
}

{% endhighlight %}

{% endtabs %}

## Initializing AutoComplete 

Import the [`SfAutoComplete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html) namespace in your page as shown below:

{% tabs %}

{% highlight xaml %}

xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;

{% endhighlight %}

{% endtabs %}

Then initialize an empty AutoComplete control as shown below:

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout 
        VerticalOptions="Start" 
        HorizontalOptions="Start"
        Padding="30">
        <autocomplete:SfAutoComplete x:Name="autoComplete"
                                     HeightRequest="40"/>
    </StackLayout>
</ContentPage>
	
{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Populating AutoComplete with Data

Now, let's create a simple list of country names and set it as the [`AutoCompleteSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_AutoCompleteSource) of the AutoComplete control:

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout 
        VerticalOptions="Start" 
        HorizontalOptions="Start"
        Padding="30">
        <autocomplete:SfAutoComplete x:Name="autoComplete"
                                     HeightRequest="40">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>India</x:String>
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>Canada</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>France</x:String>
                    <x:String>United Kingdom</x:String>
                    <x:String>China</x:String>
                    <x:String>United States</x:String>
                    <x:String>Japan</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>
</ContentPage>
	
{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                AutoCompleteSource = new List<string>()
                {
                    "India",
                    "Uganda",
                    "Ukraine", 
                    "Canada",
                    "United Arab Emirates",
                    "France", 
                    "United Kingdom",
                    "China", 
                    "United States",
                    "Japan",
                    "Angola"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

Refer [this](https://help.syncfusion.com/xamarin/autocomplete/populating-data) link to learn more about the options available in [`SfAutoComplete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html) to populate data.

## Configuring filter options

By default, items are filtered in [`“StartsWith”`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SuggestionMode.html#Syncfusion_SfAutoComplete_XForms_SuggestionMode_StartsWith) case insensitive mode and the suggestions are displayed in a drop down popup. Autocomplete can now filter suggestions.

Here in this example, let us configure it to [`“Contains”`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SuggestionMode.html#Syncfusion_SfAutoComplete_XForms_SuggestionMode_Contains) case sensitive filter mode. This can be achieved by setting [`SuggestionMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SuggestionMode) property.
 
{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout 
        VerticalOptions="Start" 
        HorizontalOptions="Start"
        Padding="30">
        <autocomplete:SfAutoComplete x:Name="autoComplete"
                                     HeightRequest="40"
                                     SuggestionMode="ContainsWithCaseSensitive">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>India</x:String>
                    <x:String>Uganda</x:String>
                    <x:String>Ukraine</x:String>
                    <x:String>Canada</x:String>
                    <x:String>United Arab Emirates</x:String>
                    <x:String>France</x:String>
                    <x:String>United Kingdom</x:String>
                    <x:String>China</x:String>
                    <x:String>United States</x:String>
                    <x:String>Japan</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };

            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                SuggestionMode = SuggestionMode.ContainsWithCaseSensitive,
                AutoCompleteSource = new List<string>()
                {
                    "India",
                    "Uganda",
                    "Ukraine", 
                    "Canada",
                    "United Arab Emirates",
                    "France", 
                    "United Kingdom",
                    "China", 
                    "United States",
                    "Japan",
                    "Angola"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

Refer [this](https://help.syncfusion.com/xamarin/autocomplete/autocomplete-filtering-options) link to learn more about the options available in SfAutoComplete to filter suggestions.

![Image-casesensitive](images/Getting-Started/contains-casesensitive.png)

The complete Getting Started sample is available in [this](https://github.com/SyncfusionExamples/xamarin.forms-sfautocomplete) link.