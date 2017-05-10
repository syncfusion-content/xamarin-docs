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

Refer [this](https://help.syncfusion.com/xamarin/introduction/download-and-installation) section to know the steps for obtaining Essential Studio components in your solution; then refer this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfautocomplete) to know the dependency assemblies details for adding AutoComplete to your project.
After adding the assemblies reference, an additional step is required for iOS and UWP projects.

### Additional Step for iOS

Create an instance of SfAutoCompleteRenderer in FinishedLaunching overridden method of AppDelegate class in iOS project as shown below:

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

There is a known Framework issue in UWP platform Release mode. Custom controls will not render in UWP if the application is deployed in Release mode. This issue can be resolved by initializing the SfAutoComplete assemblies in OnLaunched overridden method of App class in UWP project as shown in below highlighted code example:

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

	<StackLayout VerticalOptions="Center" HorizontalOptions="Center">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete"/>
	</StackLayout>
	
{% endhighlight %}

{% highlight c# %}

	StackLayout layout = new StackLayout() { VerticalOptions = LayoutOptions.Center, HorizontalOptions = LayoutOptions.Center };
	SfAutoComplete autoComplete = new SfAutoComplete() { HeightRequest = 40 };
	layout.Children.Add(autoComplete);
	Content = layout;

{% endhighlight %}

{% endtabs %}

## Populating AutoComplete with Data

Now, let us create a simple list of country names and set it as the DataSource of AutoComplete.

{% highlight c# %}

	List<String> countryNames = new List<String>();
	countryNames.Add("Great Britain");
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

## Configuring filter options

By default, items are filtered in “StartsWith” case insensitive mode and the suggestions are displayed in a drop down popup. Autocomplete can now filter suggestions and it is shown below: 

![](images/getting-started.png)

Here in this example, let us configure it to “Contains” case sensitive filter mode. This can be achieved by setting SuggestionMode property.
 
{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="ContainsWithCaseSensitive"/>
	</StackLayout> 

{% endhighlight %}

{% highlight c# %}

	autoComplete.SuggestionMode = Syncfusion.SfAutoComplete.XForms.SuggestionMode.ContainsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}