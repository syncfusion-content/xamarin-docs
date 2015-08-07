---
layout: post
title: Getting-Started
description: getting started
platform: xamarin
control: Control Name undefined
documentation: ug
---

### Getting Started

This section provides a quick overview for working with Essential RangeSlider for Xamarin.Forms.

Add Syncfusion assembly reference

Add the required Syncfusionassembly references to the respective projects as follows. Refer to the following installed location for the required assemblies.

_{Syncfusion Installed location}\Essential Studio\12.4.0.34\lib_

_Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.4.0.34\lib_

PCL project

XForms\Syncfusion. SfRangeSlider.XForms.dll 

Android project

Android\Syncfusion. SfRangeSlider.Andriod.dll

Android\Syncfusion. SfRangeSlider. XForms.Andriod.dll

iOS project

iOS\Syncfusion. SfRangeSlider.iOS.dll  

iOS\Syncfusion. SfRangeSlider.XForms.iOS.dll

Windows Phone project

WinPhone\Syncfusion. SfRangeSlider.WP8.dll

WinPhone\Syncfusion. SfRangeSlider.XForms.WinPhone.dll

> ![http://help.syncfusion.com/ug/xamarin/ImagesExt/image9_9.jpg](Getting-Started_images/Getting-Started_img1.jpeg)
{:.image }
_Note: Essential BusyIndicator for Xamarin is compatible with Xamarin Forms 1.3._

An additional step is required for Windows Phone and iOS projects. Create an instance of the RangeSlider custom renderer as follows.

Create an instance of the SfRangeSliderRenderer in MainPage constructor in Windows Phone project as follows.

public MainPage()

       	 {

           		 new SfRangeSliderRenderer ();

        		    ...    

     	}



Create an instance of the SfRangeSliderRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

        	{

         		  ...

         		  new SfRangeSliderRenderer ();

        		   ...

       	 }

Add and configure the RangeSlider

The RangeSlider control is configured entirely in C# code or using XAML markup.

Create an instance of SfRangeSlider

[C#]

// Update App.cs source in this file.

using Syncfusion.XForms.SfRangeSlider;

…

…

public class App : Application
    {
        public App()
        {
            MainPage = new RangeSliderPage ();
        }

    }

public class RangeSliderPage : ContentPage

{
        SfRangeSlider sfrangeslider;
        public BusyIndicatorPage ()
        {
            sfrangeslider = new SfRangeSlider();

        }

}



[XAML]

Use this in App.CS source.

&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ContentPage xmlns="http://xamarin.com/schemas/2014/forms" BackgroundColor="White" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="RangeSliderGettingStarted.RadialSliderPage" xmlns:syncfusion="clr-namespace:Syncfusion.SfRangeSlider.XForms;assembly=Syncfusion.SfRangeSlider.XForms"&gt;
    &lt;ContentPage.Content&gt;
            &lt;syncfusion:SfRangeSlider /&gt;
    &lt;/ContentPage.Content&gt;
&lt;/ContentPage&gt; &lt;/ContentPage.Content&gt;
&lt;/ContentPage&gt;



Configure the RangeSlider Properties

Add the RangeSlider properties in your application.

[C#]

SfBusyIndicator sfbusyindicator = new SfBusyIndicator();
sfbusyindicator.AnimationType = AnimationTypes.Battery;
sfbusyindicator.ViewBoxWidth = 150;
sfbusyindicator.ViewBoxHeight = 150;
sfbusyindicator.BackgroundColor = Color.White;



[XAML]

&lt;syncfusion:SfRangeSlider HeightRequest="100" TickFrequency="2" Minimum="0" Maximum="12" TickPlacement="BottomRight" ShowRange="True" RangeStart="4" RangeEnd="8" Orientation="Horizontal" WidthRequest="400"&gt;
        &lt;/syncfusion:SfRangeSlider&gt;



The following screenshot illustrates the output.

![](Getting-Started_images/Getting-Started_img2.png)
{:.image }


