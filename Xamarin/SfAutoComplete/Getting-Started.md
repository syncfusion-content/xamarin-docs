---
layout : post
title : Getting Started with Syncfusion AutoComplete Control for Xamarin.Forms
description : A quick tour to initial users on Syncfusion autocomplete control for Xamarin.Forms platform
platform : Xamarin
control : AutoComplete
documentation : ug
---

# Getting Started

This section explains you the steps to configure a SfAutoComplete control in a real-time scenario and also provides a walk-through on some of the customization features available in SfAutoComplete control.

## Referencing Essential Studio Components in Your Solution	

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib


You can then add the assembly references to the respective projects as shown below

{% tabs %}

{% highlight PCL %}
pcl\Syncfusion.SfAutoComplete.XForms.dll
{% endhighlight %}

{% highlight Android %}
android\Syncfusion.SfAutoComplete.Android.dll
android\Syncfusion.SfAutoComplete.XForms.Android.dll
android\Syncfusion.SfAutoComplete.XForms.dll
{% endhighlight %}

{% highlight iOS %}
iOS-unified\Syncfusion.SfAutoComplete.iOS.dll
iOS-unified\Syncfusion.SfAutoComplete.XForms.iOS.dll
iOS-unified\Syncfusion.SfAutoComplete.XForms.dll
{% endhighlight %}

{% highlight Windows %}
### Windows Phone
wp8\Syncfusion.SfInput.WP8.dll
wp8\Syncfusion.SfShared.WP8.dll
wp8\Syncfusion.SfAutoComplete.XForms.dll
wp8\Syncfusion.SfAutoComplete.XForms.WinPhone.dll

### Windows Phone 8.1
wp81\Syncfusion.SfInput.WP.dll
wp81\Syncfusion.SfShared.WP.dll
wp81\Syncfusion.SfAutoComplete.XForms.dll
wp81\Syncfusion.SfAutoComplete.XForms.WinPhone.dll
{% endhighlight %}

{% highlight WinRT %}
winrt\Syncfusion.SfInput.WinRT.dll
winrt\Syncfusion.SfShared.WinRT.dll
winrt\Syncfusion.SfAutoComplete.XForms.dll
winrt\Syncfusion.SfAutoComplete.XForms.WinRT.dll
{% endhighlight %}

{% highlight UWP %}
uwp\Syncfusion.SfInput.UWP.dll
uwp\Syncfusion.SfShared.UWP.dll
uwp\Syncfusion.SfAutoComplete.XForms.dll
uwp\Syncfusion.SfAutoComplete.XForms.UWP.dll
{% endhighlight %}

{% endtabs %}


Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the autocomplete custom renderer as shown below. 

Create an instance of SfAutoCompleteRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1 project as shown 

{% highlight C# %}

public MainPage()

{
 new SfAutoCompleteRenderer();  
}

{% endhighlight %}

Create an instance of SfAutoCompleteRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{
    new SfAutoCompleteRenderer ();
}	

{% endhighlight %}

## Add and Configure the SfAutoComplete

The following steps help to add a SfAutoComplete control through code.

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfAutoComplete.XForms;

{% endhighlight %}

{% highlight xaml %}

	<xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"/>

{% endhighlight %}

{% endtabs %}

* Now add the SfAutoComplete control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight c# %}

	SfAutoComplete countryAutoComplete = new SfAutoComplete ();

{% endhighlight %}

{% highlight xaml %}

	<autocomplete:SfAutoComplete x:Name="countryAutoComplete"/>
	
{% endhighlight %}

{% endtabs %}

## Setting AutoCompleteSource

You can set the suggestion list to the SfAutoComplete using the `AutoCompleteSource` property. Check autocomplete mode for more details.

{% tabs %}

{% highlight c# %}

    List<String> countryName = new List<String>();
	countryName.Add("Uganda");
	countryName.Add("Ukraine");
	countryName.Add("United Arab Emirates");
	countryName.Add("United Kingdom");
	countryName.Add("United States");	
	countryAutoComplete.AutoCompleteSource = countryName;

{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" HeightRequest="40" AutoCompleteSource="{Binding }" />

{% endhighlight %}

{% endtabs %}

## Adding Customizations

SfAutocomplete can be customized using the `Watermark` and `PopupDelay` properties.

{% tabs %}

{% highlight c# %}

	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	countryAutoComplete.MaximumDropDownHeight = 200;
	countryAutoComplete.MinimumPrefixCharacters = 1;
	countryAutoComplete.HeightRequest = 40;
	countryAutoComplete.PopUpDelay = 100;
	countryAutoComplete.Watermark = "Enter a country name";  

{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete Watermark="Enter a country name" x:Name="countryAutoComplete" SuggestionMode="StartsWith" AutoCompleteMode="Suggest" HeightRequest="40" MinimumPrefixCharacters="1" MaximumDropDownHeight="200" PopUpDelay ="100" />

{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)