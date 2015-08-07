---
layout: post
title: Getting-Started
description: getting started
platform: xamarin
control: Control Name undefined
documentation: ug
---

# Getting Started

This section provides a quick overview for working with Essential BusyIndicator for Xamarin.Forms.

## Add Syncfusion assembly reference

Add the required Syncfusionassembly references to the respective projects as follows. Refer to the following installed location for the required assemblies.

_{Syncfusion Installed location}\Essential Studio\12.4.0.34\lib_

_Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.4.0.34\lib_

### PCL project

XForms\Syncfusion. SfBusyIndicator.XForms.dll 

### Android project

Android\Syncfusion. SfBusyIndicator.Andriod.dll

Android\Syncfusion. SfBusyIndicator. XForms.Andriod.dll

### iOS project

iOS\Syncfusion. SfBusyIndicator.iOS.dll  

iOS\Syncfusion. SfBusyIndicator.XForms.iOS.dll

### Windows Phone project

WinPhone\Syncfusion. SfBusyIndicator.WP8.dll

WinPhone\Syncfusion. SfBusyIndicator.XForms.WinPhone.dll

![http://help.syncfusion.com/ug/xamarin/ImagesExt/image9_9.jpg](Getting-Started_images/Getting-Started_img1.jpeg)
_Note: Essential BusyIndicator for Xamarin is compatible with Xamarin Forms 1.3._

An additional step is required for Windows Phone and iOS projects. Create an instance of the BusyIndicator custom renderer as follows.

Create an instance of the SfBusyIndicatorRenderer in MainPage constructor in Windows Phone project as follows.

{% highlight c# %}
 
    [C#]

    public MainPage()

       	 {

           		 new SfBusyIndicatorRenderer ();

        		    ...    

     	}

 {% endhighlight %}


Create an instance of the SfBusyIndicatorRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows

{% highlight c# %}
 
    [C#]

    public override bool FinishedLaunching(UIApplication app, NSDictionary options)

        	{

         		  ...

         		  new SfBusyIndicatorRenderer ();

        		   ...

       	 }

 {% endhighlight %}



## Add and configure the BusyIndicator

The BusyIndicator control is configured entirely in C# code or using XAML markup.

Create an instance of SfBusyIndicator

{% highlight c# %}
 
    [C#]

// Update App.cs source in this file.

using Syncfusion.XForms.SfBusyIndicator;

…

…

public class App : Application
    {
        public App()
        {
            MainPage = new BusyIndicatorPage ();
        }

    }

public class BusyIndicatorPage : ContentPage

{
        SfBusyIndicator sfbusyindicator;
        public BusyIndicatorPage ()
        {
            sfbusyindicator = new SfBusyIndicator();

        }

}

 {% endhighlight %}



{% highlight xml %}
 
    [XAML]

    // Use this in App.CS source.

    <?xml version="1.0" encoding="UTF-8"?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"             x:Class="BusyIndicatorGettingStarted.BusyIndicatorGettingStarted" BackgroundColor="White"            xmlns:syncfusion="clr-namespace:Syncfusion.SfBusyIndicator.XForms;assembly=Syncfusion.SfBusyIndicator.XForms"            xmlns:picker="clr-namespace:BusyIndicatorGettingStarted;assembly=BusyIndicatorGettingStarted">
    <ContentPage.Content> x:Class="BusyIndicatorGettingStarted.Sample">
    <ContentPage.Content>
    <syncfusion:SfBusyIndicator      </ContentPage.Content>
    </ContentPage>

 {% endhighlight %}





### Configure the BusyIndicator Properties

Add the BusyIndicator properties in your application.

{% highlight c# %}
 
    [C#]

SfBusyIndicator sfbusyindicator = new SfBusyIndicator();
sfbusyindicator.AnimationType = AnimationTypes.Battery;
sfbusyindicator.ViewBoxWidth = 150;
sfbusyindicator.ViewBoxHeight = 150;
sfbusyindicator.BackgroundColor = Color.White;

 {% endhighlight %}



{% highlight xml %}
 
    [XAML]

    <syncfusion:SfBusyIndicator x:Name="sfbusyindicator" BackgroundColor="White" ViewBoxHeight="150" ViewBoxWidth="150" AnimationType="Ball"/>


 {% endhighlight %}





The following screenshot illustrates the output.

![](Getting-Started_images/Getting-Started_img2.png)


