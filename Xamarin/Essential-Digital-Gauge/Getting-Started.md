---
layout: post
title: Getting-Started
description: getting started
platform: xamarin
control: Control Name undefined
documentation: ug
---

# Getting Started

This section provides a quick overview for working with Essential Digital Gauge for Xamarin.Forms. 

## Add Syncfusion assembly reference

Add the required Syncfusionassembly references to the respective projects as follows. Refer to the following installed location for the required assemblies. 

_{Syncfusion Installed location}\Essential Studio\12.3.0.23\lib_

_Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.3.0.23\lib_

### PCL project

XForms\Syncfusion. SfGauge.XForms.dll  

### Android project

Android\Syncfusion. SfGauge.Andriod.dll

Android\Syncfusion. SfGauge. XForms.Andriod.dll 

### iOS project

iOS\Syncfusion. SfGauge.iOS.dll   

iOS\Syncfusion. SfGauge.XForms.iOS.dll

### Windows Phone project

WinPhone\Syncfusion. SfGauge.WP8.dll

WinPhone\Syncfusion SfGauge.XForms.WinPhone.dll

 ![C:/Users/Giftline/Desktop/img.jpg](Getting-Started_images/Getting-Started_img1.jpeg)
_Note: Essential Digital Gauge for Xamarin is compatible with Xamarin Forms 1.2.2.0._



An additional step is required for Windows Phone and iOS projects. Create an instance of the Digital Gauge custom renderer as follows.

Create an instance of the SfDigitalGaugeRenderer in MainPage constructor in Windows Phone project as follows.

{% highlight c# %}
 
    [C#]

    public MainPage()

       	 {

           		 new SfDigitalGaugeRenderer ();

        		    ...    

     	}

 {% endhighlight %}





Create an instance of the SfDigitalGaugeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

{% highlight c# %}
 
    [C#]

    public override bool FinishedLaunching(UIApplication app, NSDictionary options)

        	{

         		  ...

         		  new SfDigitalGaugeRenderer ();

        		   ...

       	 }

 {% endhighlight %}



## Add and configure the gauge

The Gauge control is configured entirely in C# code or using XAML markup.

Create an instance of SfDigitalrGauge.

{% highlight c# %}
 
    [C#]

// Update App.cs source this file.

using Syncfusion.XForms.SfGauge;

…

…

public static Page GetMainPage()

{

                  SfDigitalGauge digitalGauge = new SfDigitalGauge();

       return new ContentPage

       {

       	Content = digitalGauge,

       };

}

 {% endhighlight %}



{% highlight xml %}
 
    [XAML]

// Use the following in App.CS source.

//public static Page GetMainPage()

//{

//	return Sample();

//}

<?xml version="1.0" encoding="UTF-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"xmlns:local="clr-namespace:Syncfusion.XForms.SfGauge; assembly=Syncfusion..XForms.SfGauge "  xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="DigitalGaugeGettingStarted.Sample">

<ContentPage.Content>
<local:SfDigitalGauge>

  </local:SfDigitalGauge>

</ContentPage.Content>
</ContentPage>

 {% endhighlight %}



## Configure the Digital Gauge Properties

Add the Digital Gauge properties in your application.

{% highlight c# %}
 
   [C#]

SfDigitalGauge DigitalGauge = new SfDigitalGauge();



digitalGauge1.Value = "SYNCFUSION";

digitalGauge1.CharacterType = CharacterType.SegmentSeven;

digitalGauge1.CharacterHeight = 58;

digitalGauge1.CharacterWidth= 29;

digitalGauge1.SegmentThickness = 3;

digitalGauge1.DisabledColorOpacity = 30;

digitalGauge1.BackgroundColor = Color.FromRgb (235, 235, 235);

digitalGauge1.CharacterForeColor = Color.FromRgb (20,108,237);

digitalGauge1.CharacterDisabledColor = Color.FromRgb (20,108,237);

 {% endhighlight %}



{% highlight xml %}
 
    [XAML]

<gauge:SfDigitalGauge 

                 Value="SYNCFUSION" CharacterHeight="58"

                 CharacterWidth ="29" SegmentThickness="3" 

                 DisapledColorOpacity="30" >  

</gauge:SfCircularGauge>

 {% endhighlight %}





[http://www.syncfusion.com/Content/en-US/products/Images/Xamarin/digitalgauge/digitalgauge.png](http://www.syncfusion.com/Content/en-US/products/Images/Xamarin/digitalgauge/digitalgauge.png)

