---
layout : post
title : Getting Started with Syncfusion AutoComplete Control for Xamarin.Forms
description : A quick tour to initial users on Syncfusion autocomplete control for Xamarin.Forms platform
platform : xamarin
control : SfAutoComplete
documentation : ug
---

# Getting Started

This section explains the steps to create AutoComplete, populate it with data and filter the suggestions. This section covers only the minimal features that are needed to get started with the AutoComplete.

## Adding AutoComplete References

Refer [this](https://help.syncfusion.com/xamarin/introduction/download-and-installation) section to know the steps for obtaining Essential Studio components in your solution; then refer this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfautocomplete) to know the dependency assembly details for adding AutoComplete to your project.
After adding the assembly reference, an additional step is required for iOS and UWP projects.

### Additional Step for iOS

Create an instance of `SfAutoCompleteRenderer` in FinishedLaunching overridden method of an AppDelegate class in iOS project as shown below:

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
new Syncfusion.SfAutoComplete.XForms.iOS.SfAutoCompleteRenderer();

global::Xamarin.Forms.Forms.Init();

LoadApplication(new App());

return base.FinishedLaunching(app, options);
}	

{% endhighlight %}

### Additional Step for UWP

This step is required only if the application is deployed in Release mode with .NET native tool chain enabled and it is for resolving the known Framework issue “Custom controls not rendering in Release mode” in UWP platform. Initializing the SfAutoComplete assembly at OnLaunched overridden method of the App class in UWP project is the suggested workaround. And the code example is shown below:

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

## Initializing AutoComplete 

Import the SfAutoComplete namespace in respective Page as shown below:

{% tabs %}

{% highlight xaml %}

xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;

{% endhighlight %}

{% endtabs %}

Then initialize an empty autocomplete as shown below,

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete"/>
</StackLayout>
	
{% endhighlight %}

{% highlight c# %}

StackLayout layout = new StackLayout()
{ 
VerticalOptions = LayoutOptions.Start, 
HorizontalOptions = LayoutOptions.Start,
Padding = new Thickness(30) 
};
SfAutoComplete autoComplete = new SfAutoComplete() 
{
HeightRequest = 40 
};
layout.Children.Add(autoComplete);
Content = layout;

{% endhighlight %}

{% endtabs %}

## Populating AutoComplete with Data

Now, let us create a simple list of country names and set it as the `DataSource` of AutoComplete.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete"/>
</StackLayout>
	
{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("Canada");
countryNames.Add("United Arab Emirates");
countryNames.Add("France");
countryNames.Add("United Kingdom");
countryNames.Add("China");
countryNames.Add("United States");
countryNames.Add("Japan");
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}

Refer [this](https://help.syncfusion.com/xamarin/sfautocomplete/populating-data) link to learn more about the options available in SfAutoComplete to populate data.

## Configuring filter options

By default, items are filtered in “StartsWith” case insensitive mode and the suggestions are displayed in a drop down popup. Autocomplete can now filter suggestions.

Here in this example, let us configure it to “Contains” case sensitive filter mode. This can be achieved by setting `SuggestionMode` property.
 
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="ContainsWithCaseSensitive"/>
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("Canada");
countryNames.Add("United Arab Emirates");
countryNames.Add("France");
countryNames.Add("United Kingdom");
countryNames.Add("China");
countryNames.Add("United States");
countryNames.Add("Japan");
autoComplete.DataSource = countryNames;
autoComplete.SuggestionMode = Syncfusion.SfAutoComplete.XForms.SuggestionMode.ContainsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

Refer [this](https://help.syncfusion.com/xamarin/sfautocomplete/autocomplete-filtering-options) link to learn more about the options available in SfAutoComplete to filter suggestions.

![Image-casesensitive](images/Getting-Started/contains-casesensitive.png)

The complete Getting Started sample is available in [this](http://www.syncfusion.com/downloads/support/directtrac/general/ze/AutoComplete_GettingStarted67906545) link.