---
layout : post
title : Getting Started with Syncfusion AutoComplete Control for Xamarin.Forms
description : A quick tour to initial users on Syncfusion autocomplete control for Xamarin.Forms platform
platform : Xamarin.Forms
control : AutoComplete
documentation : ug
---

# Getting Started

This section explains you the steps to configure a AutoComplete control in a real-time scenario and also provides a walk-through on some of the customization features available in AutoComplete control.

![](images/gettingstarted.png)

## Referencing Essential Studio Components in Your Solution	

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively, if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib
Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder
{download location}\syncfusionessentialstudio-version\lib



You can then add the assembly references to the respective projects as shown below

**PCL Project**

pcl\Syncfusion.SfAutoComplete.XForm.dll

**Android Project**

android\Syncfusion.SfAutoComplete.Andriod.dll

android\Syncfusion.SfAutoComplete.xForms.Andriod.dll

**IOS (Classic) Project**

ios\Syncfusion.SfAutoComplete.iOS.dll

ios\Syncfusion.SfAutoComplete.xForms.iOS.dll

ios\Syncfusion.SfAutoComplete.XForm.dll

**IOS (Unified) Project**

ios-unified\Syncfusion.SfAutoComplete.iOS.dll

ios-unified\Syncfusion.SfAutoComplete.xForms.iOS.dll

ios-unified\Syncfusion.SfAutoComplete.XForm.dll

**Windows Phone Project**

wp8\Syncfusion.SfAutoComplete.WP8.dll

wp8\Syncfusion.SfAutoComplete.xForms.WinPhone.dll


## Add and Configure AutoComplete

* Adding reference to autocomplete.

{% highlight c# %}

	using Syncfusion.SfAutoComplete.XForms;

{% endhighlight %}

* Create an instance for autocomplete control and adding to application.

{% highlight c# %}

	SfAutoComplete countryAutoComplete= new SfAutoComplete ();
	SetContentView(countryAutoComplete);

{% endhighlight %}

## Manipulation AutoCompleteSource to AutoComplete

You can set the suggestion list to the AutoComplete using the AutoCompleteSource property. Check autocomplete mode for more details.

{% highlight c# %}

	private List<String> countryName = new List<String>();
	countryName.add("Afghanistan");
	countryName.add("Akrotiri");
	countryName.add("Albania");
	sfAutoComplete.AutoCompleteSource = countryName;

{% endhighlight %}

## Adding Customizations

Autocomplete can be customized using the `watermark` and `popupdelay` properties.

{% highlight c# %}

	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	countryAutoComplete.MaximumDropDownHeight = 300;
	countryAutoComplete.MinimumPrefixCharacters = 2
	countryAutoComplete.HeightRequest = 40;
	countryAutoComplete.Watermark = "Enter a country name";  

{% endhighlight %}

