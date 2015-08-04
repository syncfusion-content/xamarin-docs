---
layout: post
title: Getting-Started
description: getting started
platform: ios
control: Control Name undefined
documentation: ug
---

### Getting Started

This section provides a quick overview of working with Essential Linear Gauge for Xamarin.Forms. 

Add Syncfusion assembly reference

Add the required Syncfusionassemblyreferences to the respective projects as follows. You can find the required assemblies in the following installation folders. 

_{Syncfusion Installed location}\Essential Studio\12.3.0.23\lib_

_Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.3.0.23\lib_

PCL project

XForms\Syncfusion. SfGauge.XForms.dll  

Android project

Android\Syncfusion. SfGauge.Andriod.dll

Android\Syncfusion. SfGauge. XForms.Andriod.dll 

iOS project

iOS\Syncfusion. SfGauge.iOS.dll   

iOS\Syncfusion. SfGauge.XForms.iOS.dll

Windows Phone project

WinPhone\Syncfusion. SfGauge.WP8.dll

WinPhone\Syncfusion SfGauge.XForms.WinPhone.dll

> ![C:/Users/Giftline/Desktop/img.jpg](Getting-Started_images/Getting-Started_img1.jpeg)
{:.image }
_Note: Essential Linear Gauge for Xamarin is compatible with Xamarin Forms 1.2.2.0._

An additional step is required for Windows Phone and iOS projects. You are required to create an instance of the Linear Gauge custom renderer as follows.

Create an instance of the SfLinearGaugeRenderer in MainPage constructor in Windows Phone project as follows.

public MainPage()

       	 {

           		 new SfLinearGaugeRenderer ();

        		    ...    

     	}



Create an instance of the SfLinearGaugeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

        	{

         		  ...

         		  new SfLinearGaugeRenderer ();

        		   ...

       	 }

Add and configure the gauge

The Linear Gauge control is configured entirely in C# code or using XAML markup.

Create an instance of SfLinearGauge.

[C#]

// Update App.cs source this file.

using Syncfusion.XForms.SfGauge;

…

…



public static Page GetMainPage()

{

                  SfLinearGauge circularGauge = new SfLinearGauge();

       return new ContentPage

       {

       	Content = linearGauge,

       };

}



[XAML]

// Use the following in App.CS source.

//public static Page GetMainPage()

//{

//	return Sample();

//}

&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;ContentPage xmlns="http://xamarin.com/schemas/2014/forms"xmlns:local="clr-namespace:Syncfusion.XForms.SfGauge;assembly=Syncfusion.XForms.SfGauge "  xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="LinearGaugeGettingStarted.Sample"&gt;

&lt;ContentPage.Content&gt;
&lt;local:SfLinearGauge&gt;

  &lt;/local:SfLinearGauge&gt;

&lt;/ContentPage.Content&gt;
&lt;/ContentPage&gt;

Insert a Scale

Add one or more scales to Linear Gauge.



[C#]

linearGauge = new SfLinearGauge();

linearGauge.BackgroundColor = Color.White;

linearGauge.Orientation = Orientation.OrientationVertical;

//Scale

ObservableCollection<LinearScale> scales = new ObservableCollection<LinearScale>();

LinearScale scale = new LinearScale();

scale.MinimumValue= 0;

scale.MaximumValue =100;

            scale.Interval = 20;

scale.ScaleBarLength = 100;

            scale.LabelPostfix = "%";

scale.ScaleBarColor = Color.FromRgb(237,237,237);

			scale.LabelColor = Color.FromRgb(84,84,84); 

            scale.MinorTicksPerInterval = 1;

scale.ScaleBarSize = 20;

                     scales.Add(scale);

linearGauge.Scales = scales;



[Xaml]

&lt;gauge:SflinearGauge&gt;

    &lt;gauge.SfLinearGauge.Scales&gt;

       <gauge.Scale MinimumValue="0"

                 MaximumValue="100" ScaleBarLength="100"

                 LablePostfix="%" ScaleBarColor="230" 

                 ScaleBarColor="#EDEDED" LableColor="#545454" 

                 MinorTicksPerInterval="1" ScaleBarSize="20"  />

    &lt;/gauge.SfLinearGauge.Scales&gt;

  &lt;/gauge:SfLinearGauge&gt;

Specify Range

You can improve the readability of data by including ranges that quickly display when values fall within specific ranges.

[C#]

…

//Range

LinearRange range = new LinearRange ();

range.StartValue = 0;

range.EndValue = 50;

range.Color = Color.FromRgb(50,136,198);

range.StartWidth = 10;

range.EndWidth = 10;

range.Offset = -0.3;

scale.Ranges.Add(range);

…



[XAML]

&lt;local:SfLinearGauge&gt;

    &lt;local:SfLinearGauge:Scales&gt;

      <local:Scale MinimumValue="0"

                 MaximumValue="100" ScaleBarLength="100"

                 LablePostfix="%" ScaleBarColor="230" 

                 ScaleBarColor="#EDEDED" LableColor="#545454" 

                 MinorTicksPerInterval="1" ScaleBarSize="20"  >

        &lt;local:Scale.Ranges&gt;

             &lt;local:Range StartValue="0" EndValue="80" Color="#3288C6" Offset="-0.3" /&gt;    

        &lt;/local:Scale.Ranges&gt;

      &lt;/local:Scale&gt;

    &lt;/local:SfLinearGauge:Scales&gt;

  &lt;/local:SfLinearGauge&gt;

Add a Pointer

Create a Pointer and associate it with a scale.

[C#]

…

List<LinearPointer> pointers = new List<LinearPointer>()

//SymbolPointer

SymbolPointer symbolPointer = new SymbolPointer();

symbolPointer.Value = 50;

symbolPointer.Offset = 0.3;

symbolPointer.Color = Color.FromRgb(65,77,79);



//BarPointer

BarPointer rangePointer = new BarPointer();

            rangePointer.Value = 50;

rangePointer.Color =Color.FromRgb(206,69,69);

pointers.Add(symbolPointer);

            pointers.Add(rangePointer);

…



[XAML]

  &lt;local:SfLinearGauge&gt;

    &lt;local:SflinearGauge:Scales&gt;

      <local:Scale MinimumValue="0"

                 MaximumValue="100" ScaleBarLength="100"

                 LablePostfix="%" ScaleBarColor="230" 

                 ScaleBarColor="#EDEDED" LableColor="#545454" 

                 MinorTicksPerInterval="1" ScaleBarSize="20" >

        &lt;local:Scale.Ranges&gt;

             &lt;local:Range StartValue="0" EndValue="80" Color="#3288C6" Offset="-0.3" /&gt;    

        &lt;/local:Scale.Ranges&gt;

        &lt;local:Scale.Pointers&gt;

          <local:SymbolPointer Value="50" Color="Red" 

                                Offset="0.3" />

          &lt;local:BarPointer Value="50" Color="White"/&gt;

        &lt;/local:Scale.Pointers&gt;

      &lt;/local:Scale&gt;

    &lt;/local:SfLinearGauge:Scales&gt;

  &lt;/local:SfLinearGauge &gt;

Add a Minor and Major Ticksettings

You can customize a minor and major tick using Ticksettings that provides a way of indicating the current value.

[C#]

...

//Minor Ticks setting

			LinearTickSettings minor = new LinearTickSettings (); 

                                                  minor.Length =10;

minor.Color = Color.FromRgb(75,75,75);

minor.Thickness =1;

                                                  scale.MinorTickSettings = minor;

//Major Ticks setting

LinearTickSettings major = new LinearTickSettings ();

major.Length = 10;

major.Color = Color.FromRgb(75,75,75);

major.Thickness = 1;

                                             scale.MajorTickSettings = major;



...



[XAML]

&lt;local:SfLinearGauge&gt;

    &lt;local:SfLinearGauge:Scales&gt;

      <local:Scale MinimumValue="0"

                 MaximumValue="100" ScaleBarLength="100"

                 LablePostfix="%" ScaleBarColor="230" 

                 ScaleBarColor="#EDEDED" LableColor="#545454" 

                 MinorTicksPerInterval="1" ScaleBarSize="20" >

        &lt;local:Scale.Ranges&gt;

             &lt;local:Range StartValue="0" EndValue="80" Color="#3288C6" Offset="-0.3" /&gt;    

        &lt;/local:Scale.Ranges&gt;



        &lt;local:Scale.Pointers&gt;

          <local:SymbolPointer Value="50" Color="Red" 

                                Offset="0.3" />

          &lt;local:BarPointer Value="50" Color="White"/&gt;

        &lt;/local:Scale.Pointers&gt;

        &lt;local:Scale.MinorTickSettings &gt;

          <local:LinearTickSettings Length="10" Color="#4B4B4B" 

                                Tickness="1" />

        &lt;/local:Scale.MinorTickSettings &gt;

        &lt;local:Scale.MajorTickSettings &gt;

          <local:LinearTickSettings Length="10" Color="#4B4B4B" 

                                Tickness="1" />

        &lt;/local:Scale.MajorTickSettings &gt;



      &lt;/local:Scale&gt;

    &lt;/local:SfLinearGauge:Scales&gt;

  &lt;/local:SfLinearGauge&gt;



[http://www.syncfusion.com/Content/en-US/products/Images/Xamarin/lineargauge/lineargauge.png](http://www.syncfusion.com/Content/en-US/products/Images/Xamarin/lineargauge/lineargauge.png)

