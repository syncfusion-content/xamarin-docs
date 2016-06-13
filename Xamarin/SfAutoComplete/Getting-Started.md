---
layout : post
title : Getting Started with Syncfusion AutoComplete Control for Xamarin.Forms
description : A quick tour to initial users on Syncfusion autocomplete control for Xamarin.Forms platform
platform : Xamarin
control : AutoComplete
documentation : ug
---

# Getting Started

This section explains you the steps to configure a AutoComplete control in a real-time scenario and also provides a walk-through on some of the customization features available in AutoComplete control.

![](images/gettingstarted.png)

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

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfAutoComplete.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfAutoComplete.Android.dll<br/>android\Syncfusion.SfAutoComplete.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS (Classic)</td>
<td>ios\Syncfusion.SfAutoComplete.iOS.dll<br/>ios\Syncfusion.SfAutoComplete.XForms.iOS.dll<br/>ios\Syncfusion.SfAutoComplete.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfAutoComplete.iOS.dll<br/>ios-unified\Syncfusion.SfAutoComplete.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfAutoComplete.XForms.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfAutoComplete.XForms.dll<br/>wp8\Syncfusion.SfAutoComplete.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfAutoComplete.XForms.dll<br/>wp81\Syncfusion.SfAutoComplete.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfAutoComplete.XForms.dll<br/>winrt\Syncfusion.SfAutoComplete.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfInput.UWP.dll<br/>uwp\Syncfusion.SfShared.UWP.dll<br/>uwp\Syncfusion.SfAutoComplete.XForms.dll<br/>uwp\Syncfusion.SfAutoComplete.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the autocomplete custom renderer as shown below. 

Create an instance of SfAutoCompleteRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1 project as shown 

{% highlight C# %}

public MainPage()

{

    new SfAutoCompleteRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfAutoCompleteRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfAutoCompleteRenderer ();

    ...

}	

{% endhighlight %}

## Add and Configure the AutoComplete

* Adding reference to autocomplete.

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfAutoComplete.XForms;

{% endhighlight %}

{% highlight xaml %}

	xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"

{% endhighlight %}

{% endtabs %}

* Create an instance for autocomplete control and adding to application.

{% tabs %}

{% highlight c# %}

	SfAutoComplete countryAutoComplete = new SfAutoComplete ();

{% endhighlight %}

{% highlight xaml %}

	<autocomplete:SfAutoComplete/>
	
{% endhighlight %}

{% endtabs %}

## Manipulation AutoCompleteSource to AutoComplete

You can set the suggestion list to the AutoComplete using the AutoCompleteSource property. Check autocomplete mode for more details.

{% tabs %}

{% highlight c# %}

	private List<String> countryName = new List<String>();
	countryName.Add("Afghanistan");
	countryName.Add("Akrotiri");
	countryName.Add("Albania");
	sfAutoComplete.AutoCompleteSource = countryName;

{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" HeightRequest="40" AutoCompleteSource="{Binding }" />

{% endhighlight %}

{% endtabs %}

## Adding Customizations

Autocomplete can be customized using the `Watermark` and `PopupDelay` properties.

{% tabs %}

{% highlight c# %}

	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	countryAutoComplete.MaximumDropDownHeight = 300;
	countryAutoComplete.MinimumPrefixCharacters = 2
	countryAutoComplete.HeightRequest = 40;
	countryAutoComplete.Watermark = "Enter a country name";  

{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete Watermark="Enter a country name" x:Name="countryAutoComplete" SuggestionMode="StartsWith" AutoCompleteMode="Suggest" HeightRequest="40" MinimumPrefixCharacters="2" MaximumDropDownHeight="300" />

{% endhighlight %}

{% endtabs %}