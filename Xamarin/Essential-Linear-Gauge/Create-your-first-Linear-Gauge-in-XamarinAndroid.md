---
layout: post
title: Create-your-first-Linear-Gauge-in-XamarinAndroid
description: create your first linear gauge in xamarin.android
platform: ios
control: Control Name undefined
documentation: ug
---

#### Create your first Linear Gauge in Xamarin.Android

This section encompasses how to create the Linear Gauge for your business requirements in mobility that is required to be displayed in the Xamarin Android. You can also pass the required data to the default Linear Gauge and customize it according to your requirements. The following example demonstrates how to create a Linear Gauge representing the Memory usage.

![http://help.syncfusion.com/ug/android/ImagesExt/image76_2.png](Create-your-first-Linear-Gauge-in-XamarinAndroid_images/Create-your-first-Linear-Gauge-in-XamarinAndroid_img1.png)
{:.image }


Reference Essential Studio components in your solution

When the Essential Studio for Xamarin is installed, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\13.1.0.21\lib

> ![http://help.syncfusion.com/ug/android/ImagesExt/image81_8.png](Create-your-first-Linear-Gauge-in-XamarinAndroid_images/Create-your-first-Linear-Gauge-in-XamarinAndroid_img2.png)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac_

Add the following assembly references to the Android project.

 android\Syncfusion.SfLinearGauge.Andriod.dll

Create a Linear Gauge

To develop an application with the XamarinAndroid Linear Gauge is simple. The following steps explain how to create and configure its elements.

* Create an instance for the SfLinearGauge in the constructor and set that Linear Gauge as a content view of Activity.
* Set the orientation for the Linear Gauge as follows. Here, you can set the Orientation as Vertical.

SfLinearGauge linearGauge =  new SfLinearGauge(this);

//Initializing the Orientation

linearGauge.SetOrientation(SfLinearGauge.Orientation.Vertical);

Add a Scale

To add the scale for the Linear Gauge, the memory usage is displayed in percentage. Before adding the scale to the Linear Gauge, create your own values to the scale. Assign the scale to the Linear Gauge as follows.

    LinearScale scale = new LinearScale();

    outerScale.Minimum = 0;
            scale.Maximum = 100;
     scale.ScaleBarSize = 50;
     scale.ScaleBarLength = 100;
     scale.Interval = 20;
     scale.ScaleBarColor = Color.ParseColor("#FAECEC");
     scale.MinorTicksPerInterval = 2;
     scale.LabelFontSize = 17;
     scale.LabelColor = Color.ParseColor("#545454");
     scale.LabelPostfix = "%";

The above code example illustrates the minimum and maximum values for the scale and assigns the size and length of the scale. The interval denotes the gap between the Main ticks that is represented in the scale. Likewise the MinorTicksPerInterval denotes the number of ticks that needs to be in between the MajorTicks.

Add Ticks for the SfLinearGauge

There are two kinds of Ticks. They are major ticks and minor ticks. Major ticks are the primary scale indicators and Minor ticks are the secondary scale indicators that fall between the major ticks. The major ticks and minor ticks are customized and assigned to the scale by using the following code example.

 //Adding major ticks

LinearTickSettings scale_majorTicksSettings = new LinearTickSettings();
scale_majorTicksSettings.Color = Color.ParseColor("#AFAFAF");
scale_majorTicksSettings.Length = 20;
scale_majorTicksSettings.StrokeWidth = 5;
scale_majorTicksSettings.Offset = 0;

scale.MajorTickSettings = scale_majorTicksSettings;

//Adding minor ticks

LinearTickSettings scale_minorTicksSettings = new LinearTickSettings();

scale_minorTicksSettings.Color = Color.ParseColor("#AFAFAF");
scale_minorTicksSettings.Length = 10;
scale_minorTicksSettings.StrokeWidth = 5;
Scale_minorTicksSettings.Offset = 0;
scale.MinorTickSettings = scale_minorTicksSettings;

The above code example displays the major ticks and minor ticks for the scale assigned to the Linear Gauge.

Add Pointers

Pointer is a key element of the linear scale that points a value or measure on that scale. A linear scale can have one or more pointers that can be used to measure different values for different criteria. Each pointer has a Value property that specifies the current value of the linear scale based upon its measurement.

There are two types of Pointers. They are BarPointer and SymbolPointer. Refer to the following code example to add theSymbolPointers and BarPointer to the scale.

_//Adding Symbol Pointer_

SymbolPointer outerScale_needlePointer = new SymbolPointer();
outerScale_needlePointer.Value = pointervalue;
outerScale_needlePointer.StrokeWidth = 0;
outerScale_needlePointer.Offset = 0.3f;
outerScale_needlePointer.Color = Color.ParseColor("#414D4F");
pointers.Add(outerScale_needlePointer);

_//Adding Bar Pointer_
BarPointer rangePointer = new BarPointer();
rangePointer.Value = barvalue;
rangePointer.Color = Color.ParseColor("#CE4545");_//_
rangePointer.StrokeWidth = 20;
pointers.Add(rangePointer); 

The pointers are displayed at the defined value in the scale with the respective color and width. You are required to add this pointer to a collection and assign it to the scale.

   //Adding the pointers to the linear gauge

scale.Pointers = pointers; 



Add Range

Scale contains one or more Ranges. Range displays the start and end values of the inner divisions within the linear scale’s whole range. Each range displays different zones or regions of the same metrics: high, low and average temperature range.

//Adding ranges
            LinearRange lowerRange = new LinearRange();
            lowerRange.StartWidth = 30;
            lowerRange.EndWidth = 30;
            lowerRange.Color = Color.ParseColor("#67d6db");
            lowerRange.StartValue = 0;
            lowerRange.EndValue = 50;
            lowerRange.Offset = -.3;
            ranges.Add(lowerRange);

            LinearRange higherRange = new LinearRange();
            higherRange.StartWidth = 30;
            higherRange.EndWidth = 30;
            higherRange.Color = Color.ParseColor("#32B8C6");
            higherRange.StartValue = 50;
            higherRange.EndValue = 100;
            higherRange.Offset = -.3;
            ranges.Add(higherRange);



The above code example explains how to add multiple range to a scale. Add this ranges to a collection and assign it to the scale. Refer to the following code example.

  //Adding the range to a scale

  ObservableCollection<LinearScale> scales = new ObservableCollection<LinearScale>();
            ObservableCollection<LinearPointer> pointers = new ObservableCollection<LinearPointer>();
            ObservableCollection<LinearRange> ranges = new ObservableCollection<LinearRange>();  

ranges.Add(higherRange);  

ranges.Add(lowerRange); 

  scale.setRanges(ranges);

Finally, add this scale to a Collection and assign it to the Linear Gauge by using the following code example.

  //Adding a scale to the LinearGauge

            scales.Add(outerScale);
            linearGauge.Scales = scales;

 Now, the scales are added successfully to the Linear Gauge.

![http://help.syncfusion.com/ug/android/ImagesExt/image76_3.png](Create-your-first-Linear-Gauge-in-XamarinAndroid_images/Create-your-first-Linear-Gauge-in-XamarinAndroid_img3.png)
{:.image }


