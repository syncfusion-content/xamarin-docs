---
layout: post
title: Getting Started |  LinearGauge | Xamarin | Syncfusion
description: getting started
platform: xamarin
control: LinearGauge
documentation: ug
---

# Getting Started

This section provides a quick overview of working with Essential Linear Gauge for Xamarin.Forms. 

## Add Syncfusion assembly reference

Add the required Syncfusionassemblyreferences to the respective projects as follows. You can find the required assemblies in the following installation folders. 

{Syncfusion Installed location}\Essential Studio\12.3.0.23\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.3.0.23\lib

### PCL project

XForms\Syncfusion. SfGauge.XForms.dll  

### Android project

Android\Syncfusion. SfGauge.Android.dll

Android\Syncfusion. SfGauge. XForms.Android.dll 

### iOS project

iOS\Syncfusion. SfGauge.iOS.dll   

iOS\Syncfusion. SfGauge.XForms.iOS.dll

### Windows Phone project

WinPhone\Syncfusion. SfGauge.WP8.dll

WinPhone\Syncfusion SfGauge.XForms.WinPhone.dll



N> Essential Linear Gauge for Xamarin is compatible with Xamarin Forms 1.2.2.0.

An additional step is required for Windows Phone and iOS projects. You are required to create an instance of the Linear Gauge custom renderer as follows.

Create an instance of the SfLinearGaugeRenderer in MainPage constructor in Windows Phone project as follows.

{% highlight c# %}

public MainPage()
{

    new SfLinearGaugeRenderer ();
        		    ...    
}

{% endhighlight %}


Create an instance of the SfLinearGaugeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

{% highlight c# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    ...

    new SfLinearGaugeRenderer ();

    ...

}

{% endhighlight %}

## Add and configure the gauge

The Linear Gauge control is configured entirely in C# code or using XAML markup.

Create an instance of SfLinearGauge.

{% tabs %}  

{% highlight c# %}

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

// Use the following in App.CS source.

//public static Page GetMainPage()

//{

//	return Sample();

//}

{% endhighlight %}

{% highlight xaml %}

<?xml version="1.0" encoding="UTF-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:local="clr-namespace:Syncfusion.XForms.SfGauge;
	assembly=Syncfusion.XForms.SfGauge "  xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="LinearGaugeGettingStarted.Sample">

<ContentPage.Content>
<local:SfLinearGauge> 
	</local:SfLinearGauge>
</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% endtabs %}  

## Insert a Scale

Add one or more scales to Linear Gauge.

{% tabs %} 

{% highlight c# %}

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

{% endhighlight %}

{% highlight xaml %}

<gauge:SflinearGauge>

<gauge.SfLinearGauge.Scales>

<gauge.Scale MinimumValue="0"

    MaximumValue="100" ScaleBarLength="100"

    LablePostfix="%" ScaleBarColor="230" 

    ScaleBarColor="#EDEDED" LableColor="#545454" 

    MinorTicksPerInterval="1" ScaleBarSize="20"  />

</gauge.SfLinearGauge.Scales>

</gauge:SfLinearGauge>

{% endhighlight %}

{% endtabs %}  

## Specify Range

You can improve the readability of data by including ranges that quickly display when values fall within specific ranges.

{% tabs %}  

{% highlight c# %}

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

{% endhighlight %}


{% highlight xaml %}

<local:SfLinearGauge>

<local:SfLinearGauge:Scales>

<local:Scale MinimumValue="0"

    MaximumValue="100" ScaleBarLength="100"

    LablePostfix="%" ScaleBarColor="230" 

    ScaleBarColor="#EDEDED" LableColor="#545454" 

    MinorTicksPerInterval="1" ScaleBarSize="20"  >

<local:Scale.Ranges>

    <local:Range StartValue="0" EndValue="80" Color="#3288C6" Offset="-0.3" />    

</local:Scale.Ranges>

</local:Scale>

</local:SfLinearGauge:Scales>

</local:SfLinearGauge>

{% endhighlight %}
  
{% endtabs %}    
  
## Add a Pointer

Create a Pointer and associate it with a scale.

{% tabs %}  

{% highlight c# %}

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

{% endhighlight %}


{% highlight xaml %}

<local:SfLinearGauge>

<local:SflinearGauge:Scales>

<local:Scale MinimumValue="0"

    MaximumValue="100" ScaleBarLength="100"

    LablePostfix="%" ScaleBarColor="230" 

    ScaleBarColor="#EDEDED" LableColor="#545454" 

    MinorTicksPerInterval="1" ScaleBarSize="20" >

<local:Scale.Ranges>

    <local:Range StartValue="0" EndValue="80" Color="#3288C6" Offset="-0.3" />    

</local:Scale.Ranges>

<local:Scale.Pointers>

    <local:SymbolPointer Value="50" Color="Red" Offset="0.3" />                             

    <local:BarPointer Value="50" Color="White"/>

</local:Scale.Pointers>

</local:Scale>

</local:SfLinearGauge:Scales>

</local:SfLinearGauge >

{% endhighlight %}

{% endtabs %}  

## Add a Minor and Major Ticksettings

You can customize a minor and major tick using Ticksettings that provides a way of indicating the current value.

{% tabs %} 

{% highlight c# %}


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
{% endhighlight %}


{% highlight xaml %}

<local:SfLinearGauge>

<local:SfLinearGauge:Scales>

<local:Scale MinimumValue="0"

    MaximumValue="100" ScaleBarLength="100"

    LablePostfix="%" ScaleBarColor="230" 

    ScaleBarColor="#EDEDED" LableColor="#545454" 

    MinorTicksPerInterval="1" ScaleBarSize="20" >

<local:Scale.Ranges>

    <local:Range StartValue="0" EndValue="80" Color="#3288C6" Offset="-0.3" />    

</local:Scale.Ranges>

<local:Scale.Pointers>

<local:SymbolPointer Value="50" Color="Red"  Offset="0.3" />                             

<local:BarPointer Value="50" Color="White"/>

</local:Scale.Pointers>

<local:Scale.MinorTickSettings >

<local:LinearTickSettings Length="10" Color="#4B4B4B"  Tickness="1" />
                             
</local:Scale.MinorTickSettings >

<local:Scale.MajorTickSettings >

<local:LinearTickSettings Length="10" Color="#4B4B4B"  Tickness="1" />
                              
</local:Scale.MajorTickSettings >

</local:Scale>

</local:SfLinearGauge:Scales>

</local:SfLinearGauge>

{% endhighlight %}

{% endtabs %}  
 
[http://www.syncfusion.com/Content/en-US/products/Images/Xamarin/lineargauge/lineargauge.png](http://www.syncfusion.com/Content/en-US/products/Images/Xamarin/lineargauge/lineargauge.png)

## Create your first Linear Gauge in Xamarin.Android

This section encompasses how to create the Linear Gauge for your business requirements in mobility that is required to be displayed in the Xamarin Android. You can also pass the required data to the default Linear Gauge and customize it according to your requirements. The following example demonstrates how to create a Linear Gauge representing the Memory usage.

![](Create-your-first-Linear-Gauge-in-XamarinAndroid_images/img1.png)



### Reference Essential Studio components in your solution

When the Essential Studio for Xamarin is installed, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\13.1.0.21\lib


N> Assemblies are available in unzipped package location in Mac

Add the following assembly references to the Android project.

 android\Syncfusion.SfLinearGauge.Android.dll

### Create a Linear Gauge

To develop an application with the XamarinAndroid Linear Gauge is simple. The following steps explain how to create and configure its elements.

* Create an instance for the SfLinearGauge in the constructor and set that Linear Gauge as a content view of Activity.
* Set the orientation for the Linear Gauge as follows. Here, you can set the Orientation as Vertical.

{% highlight c# %}

SfLinearGauge linearGauge =  new SfLinearGauge(this);

//Initializing the Orientation

linearGauge.SetOrientation(SfLinearGauge.Orientation.Vertical);

{% endhighlight %}

### Add a Scale

To add the scale for the Linear Gauge, the memory usage is displayed in percentage. Before adding the scale to the Linear Gauge, create your own values to the scale. Assign the scale to the Linear Gauge as follows.

{% highlight c# %}

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

{% endhighlight %}

The above code example illustrates the minimum and maximum values for the scale and assigns the size and length of the scale. The interval denotes the gap between the Main ticks that is represented in the scale. Likewise the MinorTicksPerInterval denotes the number of ticks that needs to be in between the MajorTicks.

### Add Ticks for the SfLinearGauge

There are two kinds of Ticks. They are major ticks and minor ticks. Major ticks are the primary scale indicators and Minor ticks are the secondary scale indicators that fall between the major ticks. The major ticks and minor ticks are customized and assigned to the scale by using the following code example.

{% highlight c# %}

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

{% endhighlight %}

The above code example displays the major ticks and minor ticks for the scale assigned to the Linear Gauge.

### Add Pointers

Pointer is a key element of the linear scale that points a value or measure on that scale. A linear scale can have one or more pointers that can be used to measure different values for different criteria. Each pointer has a Value property that specifies the current value of the linear scale based upon its measurement.

There are two types of Pointers. They are BarPointer and SymbolPointer. Refer to the following code example to add theSymbolPointers and BarPointer to the scale.

{% highlight c# %}

//Adding Symbol Pointer

SymbolPointer outerScale_needlePointer = new SymbolPointer();
outerScale_needlePointer.Value = pointervalue;
outerScale_needlePointer.StrokeWidth = 0;
outerScale_needlePointer.Offset = 0.3f;
outerScale_needlePointer.Color = Color.ParseColor("#414D4F");
pointers.Add(outerScale_needlePointer);

//Adding Bar Pointer
BarPointer rangePointer = new BarPointer();
rangePointer.Value = barvalue;
rangePointer.Color = Color.ParseColor("#CE4545");
rangePointer.StrokeWidth = 20;
pointers.Add(rangePointer); 

{% endhighlight %}

The pointers are displayed at the defined value in the scale with the respective color and width. You are required to add this pointer to a collection and assign it to the scale.

{% highlight c# %}

//Adding the pointers to the linear gauge

scale.Pointers = pointers; 

{% endhighlight %}


### Add Range

Scale contains one or more Ranges. Range displays the start and end values of the inner divisions within the linear scale’s whole range. Each range displays different zones or regions of the same metrics: high, low and average temperature range.

{% highlight c# %}

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

{% endhighlight %}

The above code example explains how to add multiple range to a scale. Add this ranges to a collection and assign it to the scale. Refer to the following code example.

{% highlight c# %}

//Adding the range to a scale

ObservableCollection<LinearScale> scales = new ObservableCollection<LinearScale>();
ObservableCollection<LinearPointer> pointers = new ObservableCollection<LinearPointer>();
ObservableCollection<LinearRange> ranges = new ObservableCollection<LinearRange>();  

ranges.Add(higherRange);  

ranges.Add(lowerRange); 

scale.setRanges(ranges);

{% endhighlight %}

Finally, add this scale to a Collection and assign it to the Linear Gauge by using the following code example.

{% highlight c# %}

 //Adding a scale to the LinearGauge

scales.Add(outerScale);

linearGauge.Scales = scales;

{% endhighlight %}

Now, the scales are added successfully to the Linear Gauge.

![](Create-your-first-Linear-Gauge-in-XamarinAndroid_images/img3.png)

## Create your first Linear Gauge in Xamarin.iOS

This section encompasses how to create the Linear Gauge for your business requirements in mobility that is required to be displayed in Xamarin iOS. You can also pass the required data to the default Linear Gauge and customize it according to your requirements. The following example demonstrates how to create a Linear Gauge representing the Memory usage.

![](Create-your-first-Linear-Gauge-in-XamariniOS_images/img1.png)





### Reference Essential Studio components in your solution

When the Essential Studio for Xamarin is installed, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\13.1.0.21\lib



N> Assemblies are available in unzipped package location in Mac

Add the following assembly references to the iOS project.

 iOS\Syncfusion.SfGauge.iOS.dll

### Create a Linear Gauge

To develop an application with the XamariniOS Linear Gauge is simple. 

Create an instance of SfLinearGauge.

{% highlight c# %}

SFLinearGauge linearGauge = new SFLinearGauge();

//Initializing the Orientation

linearGauge.Orientation = SFLinearGaugeOrientation.SFLinearGaugeOrientationVertical;

{% endhighlight %}

### Add a Scale

To add the scale for the Linear Gauge, the memory usage is displayed in percentage. Before adding the scale to the Linear Gauge, create your own values to the scale. Assign the scale to the Linear Gauge as follows.

{% highlight c# %}

SFLinearScale scale = new SFLinearScale ();

scale.Minimum = 0;

scale.Maximum = 100;

scale.Interval = 20;

scale.ScaleBarLength = 100;

scale.LabelPostfix = "%";

scale.ScaleBarColor =UIColor.FromRGB (250, 236, 236);

scale.LabelColor = UIColor.FromRGB (84, 84, 84); 

scale.MinorTicksPerInterval = 1;

scale.ScaleBarSize = 13;

scale.ScalePosition = SFLinearGaugeScalePosition.SFLinearGaugeScalePositionForward;

{% endhighlight %}

The above code example illustrates the minimum and maximum values for the scale and assigns the size and length of the scale. The interval denotes the gap between the Main ticks that is represented in the scale. Likewise the MinorTicksPerInterval denotes the number of ticks that needs to be in between the MajorTicks.

### Add Ticks for the SfLinearGauge

There are two kinds of Ticks. They are major ticks and minor ticks. Major ticks are the primary scale indicators and Minor ticks are the secondary scale indicators that fall between the major ticks. The major ticks and minor ticks are customized and assigned to the scale by using the following code example.

{% highlight c# %}

 //Minor Ticks setting

SFLinearTickSettings minor = new SFLinearTickSettings ();

minor.Length = 10;

minor.Color = UIColor.FromRGB (175, 175, 175);

minor.Thickness = 1;

scale.MinorTickSettings = minor;

//Major Ticks setting

SFLinearTickSettings major = new SFLinearTickSettings ();

major.Length = 10;

major.Color = UIColor.FromRGB (175, 175, 175);

major.Thickness = 1;

scale.MajorTickSettings = major;

scale.Pointers.Add (symbolPointer);

scale.Pointers.Add (rangePointer);

linearGauge.Scales.Add (scale);
scale_minorTicksSettings.StrokeWidth = 5;
Scale_minorTicksSettings.Offset = 0;
scale.MinorTickSettings = scale_minorTicksSettings;

{% endhighlight %}

The above code example displays the majorticks and minorticks for the scale assigned to the Linear Gauge.

### Add Pointers

Pointer is a key element of the linear scale that points a value or measure on that scale. A linear scale can have one or more pointers that can be used to measure different values for different criteria. Each pointer has a Value property that specifies the current value of the linear scale based upon its measurement.

There are two types of Pointers. They are BarPointer and SymbolPointer. Refer to the following code example to add theSymbolPointers and BarPointer to the scale.

{% highlight c# %}

//SymbolPointer

SFSymbolPointer symbolPointer = new SFSymbolPointer ();

symbolPointer.Value = 50;

symbolPointer.Offset = 0;

symbolPointer.Thickness = 3;

symbolPointer.Color = UIColor.FromRGB (65, 77, 79);

//BarPointer

SFBarPointer rangePointer = new SFBarPointer ();

rangePointer.Value = 50;

rangePointer.Color = UIColor.FromRGB (206, 69, 69);

rangePointer.Thickness = 10;

{% endhighlight %}

 The pointers are displayed at the defined value in the scale with the respective color and width. You are required to add this pointer to a collection and assign it to the scale.

{% highlight c# %}

//Adding the pointers to the linear gauge

scale.Pointers.Add (symbolPointer);

scale.Pointers.Add (rangePointer);

{% endhighlight %}

### Add Range

Scale contains one or more Ranges. Range displays the start and end values of the inner divisions within the linear scale’s whole range. Each range displays different zones or regions of the same metrics: high, low and average temperature range.

{% highlight c# %}

//Adding ranges
//Range

SFLinearRange range = new SFLinearRange ();

range.StartValue = 0;

range.EndValue = 50;

range.Color = UIColor.FromRGB (234, 248, 249);

range.StartWidth = 10;

range.EndWidth = 10;

range.Offset = nfloat.Parse("-0.17");

scale.Ranges.Add (range);

{% endhighlight %}

The above code example explains how to add multiple range to a scale. Add this ranges to a collection and assign it to the scale. Refer to the following code example.

{% highlight c# %}

//Adding the range to a scale

scale.Ranges.Add (range);

scale.Ranges.Add (range2);

{% endhighlight %}

Finally, add this scale to a Collection and assign it to the Linear Gauge by using the following code example.

{% highlight c# %}

//Adding a scale to the LinearGauge

linearGauge.Scales.Add (scale);

{% endhighlight %}

Now, the scales are added successfully to the Linear Gauge.

![](Create-your-first-Linear-Gauge-in-XamariniOS_images/img3.png)