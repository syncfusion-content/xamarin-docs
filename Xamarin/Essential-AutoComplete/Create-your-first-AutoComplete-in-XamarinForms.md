---
layout: post
title: Create-your-first-AutoComplete-in-XamarinForms
description: create your first autocomplete in xamarin.forms
platform: xamarin
control: Control Name undefined
documentation: ug
---

#### Create your first AutoComplete in Xamarin.Forms

This section provides a quick overview for working with Essential AutoComplete for Xamarin.Forms.

Add Syncfusion assembly reference

Add the required Syncfusionassembly references to the respective projects as follows. Refer to the following installed location for the required assemblies.

{Syncfusion Installed location}\Essential Studio\13.2.0.29\lib

For example: C:\Program Files (x86)\Syncfusion\Essential Studio\13.2.0.29\lib

PCL project

XForms\Syncfusion. SfAutoComplete.XForms.dll 

Android project

Android\Syncfusion. SfAutoComplete.Andriod.dll

Android\Syncfusion. SfAutoComplete. XForms.Andriod.dll

iOS project

iOS\Syncfusion. SfAutoComplete.iOS.dll  

iOS\Syncfusion. SfAutoComplete.XForms.iOS.dll

Windows Phone project

WinPhone\Syncfusion. SfInput.WP8.dll

WinPhone\Syncfusion. SfShared.WP8.dll

WinPhone\Syncfusion. SfAutoComplete.XForms.WinPhone.dll

![http://help.syncfusion.com/ug/xamarin/ImagesExt/image9_9.jpg](Create-your-first-AutoComplete-in-XamarinForms_images/Create-your-first-AutoComplete-in-XamarinForms_img1.jpeg)
{:.image }
_Note: Essential AutoComplete for Xamarin is compatible with Xamarin Forms 1.3._



An additional step is required for Windows Phone and iOS projects.

Create an instance of the SfAutoCompleteRenderer in MainPage constructor of Windows Phone project as follows.

public MainPage()

       	 {

           		 new SfAutoCompleteRenderer ();

        		    ...    

     	}



Create an instance of the SfAutoCompleteRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

        	{

         		  ...

         		  new SfAutoCompleteRenderer ();

        		   ...

       	 }



Add and configure the AutoComplete

The AutoComplete control is configured entirely in C# code or by using XAML markup.

Create an instance of SfAutoComplete.

[C#]

// Update App.cs source in this file.

using Syncfusion.XForms.SfAutoComplete;

…

…

public class App : Application
    {
        public App()
        {
            MainPage = new AutoCompletePage ();
        }

    }

public class AutoCompletePage : ContentPage

{
        SfAutoComplete sfautocomplete;
        public AutoCompletePage ()
        {
            sfautocomplete = new SfAutoComplete();

        }

}



[XAML]

// Use this in App.CS source.

&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"             x:Class="AutoCompleteGettingStarted.AutoCompleteGettingStarted " BackgroundColor="White"            xmlns:syncfusion="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion. SfAutoComplete.XForms"            xmlns:picker="clr-namespace: AutoCompleteGettingStarted;assembly= AutoCompleteGettingStarted "&gt;
    &lt;ContentPage.Content&gt; x:Class=" AutoCompleteGettingStarted.Sample">

&lt;ContentPage.Content&gt;
        &lt;syncfusion:SfAutoComplete      &lt;/ContentPage.Content&gt;
&lt;/ContentPage&gt;



Configure the AutoComplete Properties

Add the AutoComplete properties in your application.

[C#]

SfAutoComplete sfautocomplete = new SfAutoComplete  ();
sfautocomplete .AutoCompleteSource= list1;
sfautocomplete .MinimumPrefixCharacter= 2;
sfautocomplete .MaximumDropDownHeight= 200;
sfautocomplete .PopUpelay= 100;



[XAML]

&lt;syncfusion:SfAutoComplete x:Name="sfautocomplete" BackgroundColor="White" MinimumPrefixCharacter="2" MaximumDropDownHeight="200" PopUpDelay="100"/&gt;




The following screenshot illustrates the output.

![](Create-your-first-AutoComplete-in-XamarinForms_images/Create-your-first-AutoComplete-in-XamarinForms_img2.png)
{:.image }


