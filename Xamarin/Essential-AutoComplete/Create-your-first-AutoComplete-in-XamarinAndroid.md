---
layout: post
title: Create-your-first-AutoComplete-in-XamarinAndroid
description: create your first autocomplete in xamarin.android
platform: ios
control: Control Name undefined
documentation: ug
---

#### Create your first AutoComplete in Xamarin.Android

This section provides a quick overview for working with AutoComplete in Android Studio. This example explains how to create an AutoComplete with different AutoCompleteModes and SuggestionModes.

![](Create-your-first-AutoComplete-in-XamarinAndroid_images/Create-your-first-AutoComplete-in-XamarinAndroid_img1.png)
{:.image }


Reference Essential Studio components in your solution

After installing the Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\13.2.0.29\lib

![](Create-your-first-AutoComplete-in-XamarinAndroid_images/Create-your-first-AutoComplete-in-XamarinAndroid_img2.jpeg)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac._

Add the following assembly references to the Xamarin project.

 android\Syncfusion.SfAutoComplete.Andriod.dll

To develop an application with the Xamarin AutoComplete is simple.

Create an instance for the SfAutoComplete in the constructor and set that AutoComplete as content view of Activity.

[C#]

SfBusyIndicator sfBusyIndicator = new SfBusyIndicator(this);

setContentView(sfBusyIndicator);



Setting the AutoCompleteSource to AutoComplete

You can set the suggestion list to the AutoComplete by using the AutoCompleteSource property and assign by using a DataAdapter. 

List<String> cList = new List<String>(); 

cList.Add ("Afghanistan"); 

cList.Add ("Akrotiri");

cList.Add ("Albania");
cList.Add ("Algeria"); 

ArrayAdapter<String> adapters = new ArrayAdapter<String>(con,
                Android.Resource.Layout.SimpleListItem1, new Countrylist().Country);
autoComplete1.SetAutoCompleteSource(adapters);  



Setting AutoComplete Customizations

AutoComplete is customized by setting the properties as explained in the following code example.

 autoComplete1.SuggestionMode = SuggestionMode.StartsWith;
 autoComplete1.MaximumDropDownHeight = 200;
 autoComplete1.Watermark = "Enter a country name";
 autoComplete1.PopUpDelay = 100;
 autoComplete1.AutoCompleteMode = AutoCompleteMode.Append;
 autoComplete1.MinimumPrefixCharacters = 2; 



