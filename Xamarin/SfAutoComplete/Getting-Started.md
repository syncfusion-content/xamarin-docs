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

## Add SfAutoComplete

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
<td>android\Syncfusion.SfAutoComplete.Android.dll<br/>android\Syncfusion.SfAutoComplete.XForms.Android.dll<br/>android\Syncfusion.SfAutoComplete.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfAutoComplete.iOS.dll<br/>iOS-unified\Syncfusion.SfAutoComplete.XForms.iOS.dll<br/>iOS-unified\Syncfusion.SfAutoComplete.XForms.dll</td>
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

{% tabs %}

{% highlight C# %}

public MainPage()
{
    new SfAutoCompleteRenderer();  
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfAutoCompleteRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfAutoCompleteRenderer ();
}	

{% endhighlight %}

{% endtabs %}

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	<xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"/>

{% endhighlight %}

{% highlight c# %}

	using Syncfusion.SfAutoComplete.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the SfAutoComplete control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

	<ContentPage.Content>
		<autocomplete:SfAutoComplete x:Name="autocomplete"/>
	</ContentPage.Content>
	
{% endhighlight %}

{% highlight c# %}

	SfAutoComplete countryAutoComplete = new SfAutoComplete ();
	this.Content = countryAutoComplete;

{% endhighlight %}

{% endtabs %}

## Add Items

A list of string with country names are created and added to auto complete source. This list will be populated as suggestion list based on text entry.

{% tabs %}

{% highlight c# %}
	SfAutoComplete countryAutoComplete = new SfAutoComplete ();
    List<String> countryName = new List<String>();
	countryName.Add("Uganda");
	countryName.Add("Ukraine");
	countryName.Add("United Arab Emirates");
	countryName.Add("United Kingdom");
	countryName.Add("United States");	
	countryAutoComplete.AutoCompleteSource = countryName;
	this.Content = countryAutoComplete;
{% endhighlight %}

{% endtabs %}


## Set Filter Mode

Filters can be applied to the displayed items based on starting letter. We can also append the first item from the suggested list to the TextBox. This can be done by using the `SuggestionMode` and `AutoCompleteMode` properties in SfAutoComplete control.

The following example shows the SfAutoComplete control which suggest the country list starting with the letter U.
 
{% tabs %}

{% highlight xaml %}

<ContentPage.Content>
   <autocomplete:SfAutoComplete Watermark="Enter a country name" x:Name="countryAutoComplete" SuggestionMode="StartsWith" AutoCompleteMode="Suggest" HeightRequest="40" MinimumPrefixCharacters="1" MaximumDropDownHeight="200" />
</ContentPage.Content>
{% endhighlight %}

{% highlight c# %}
	SfAutoComplete countryAutoComplete = new SfAutoComplete ();	
	countryAutoComplete.SuggestionMode = SuggestionMode.StartsWith;
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	countryAutoComplete.MaximumDropDownHeight = 200;
	countryAutoComplete.MinimumPrefixCharacters = 1;
	countryAutoComplete.HeightRequest = 40;
	
	List<String> countryName = new List<String>();
	countryName.Add("Uganda");
	countryName.Add("Ukraine");
	countryName.Add("United Arab Emirates");
	countryName.Add("United Kingdom");
	countryName.Add("United States");	
	
	countryAutoComplete.AutoCompleteSource = countryName;
	countryAutoComplete.Watermark = "Enter a country name";  

	this.Content = countryAutoComplete;

{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)