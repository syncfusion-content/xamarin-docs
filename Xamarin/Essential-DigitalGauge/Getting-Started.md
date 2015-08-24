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

{Syncfusion Installed location}\Essential Studio\12.3.0.23\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.3.0.23\lib

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

 
N> Essential Digital Gauge for Xamarin is compatible with Xamarin Forms 1.2.2.0.



An additional step is required for Windows Phone and iOS projects. Create an instance of the Digital Gauge custom renderer as follows.

Create an instance of the SfDigitalGaugeRenderer in MainPage constructor in Windows Phone project as follows.

{% highlight c# %}
 
  

    public MainPage()

       	 {

           		 new SfDigitalGaugeRenderer ();

        		    ...    

     	}

 {% endhighlight %}





Create an instance of the SfDigitalGaugeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

{% highlight c# %}
 
  

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
 
    

<gauge:SfDigitalGauge 

                 Value="SYNCFUSION" CharacterHeight="58"

                 CharacterWidth ="29" SegmentThickness="3" 

                 DisapledColorOpacity="30" >  

</gauge:SfCircularGauge>

 {% endhighlight %}





[http://www.syncfusion.com/Content/en-US/products/Images/Xamarin/digitalgauge/digitalgauge.png](http://www.syncfusion.com/Content/en-US/products/Images/Xamarin/digitalgauge/digitalgauge.png)

## Create your first Digital Gauge in Xamarin.Android

This section provides a quick overview for working with the Essential Digital Gauge for Xamarin Android. It guides you to the entire process of creating a real-world chart. You can how to create a Digital Gauge to display the time similar to a digital clock with different Character Types.

![](Create-your-first-Digital-Gauge-in-XamarinAndroid_images/Create-your-first-Digital-Gauge-in-XamarinAndroid_img1.jpeg)



### Reference Essential Studio components in your solution

When the Essential Studio for Xamarin is installed, all the required assemblies can be found in the installation folders: {Syncfusion Installed location}\Essential Studio\13.1.0.21\lib


N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the Android project.

 [android\Syncfusion.SfDigitalGauge.Andriod.dll]



### Create a Digital Gauge

To develop an application with the XamarinAndroid Digital Gauge is simple. 

Create an instance for the SfDigitalGauge in the constructor and set the Digital Gauge as the content view of Activity.

{% highlight c# %}
 
  

   SfDigitalGauge digitalGauge1 = new SfDigitalGauge(this);

SetContentView (digitalGauge1);

 {% endhighlight %}





### Add values to display

You can set the value for the gauge by using the setValue() in the Digital Gauge. It can be Alphabet, Numbers, or Special Characters.

{% highlight c# %}
 
  

     SimpleDateFormat sdf = new SimpleDateFormat("HH mm ss");
string currentDateandTime = sdf.Format(new Date()); 

//Sets the gauge value.

digitalGauge1.Value = currentDateandTime;

 {% endhighlight %}



 The above code example explains how the values are assigned to the Digital Gauge. You can obtain the Time by using the SimpleDateFormat and that is assigned to the Digital Gauge. 

### Set Digital Gauge customizations

The Digital Gauge is customized by setting the properties as explained in the following code example.

{% highlight c# %}
 
  

    //Sets the character stroke color.

digitalGauge1. CharacterStroke = Color.Rgb(20,108,237);

//Sets the character height.

digitalGauge1. CharacterHeight = 25 ;

//Sets the character spacing.

digitalGauge1. CharactersSpacing = 2;

//Sets the character width.

digitalGauge1. CharacterWidth = 12;

//Sets the segment stroke width.

digitalGauge1. SegmentStrokeWidth = 2;

//Sets the character type to be displayed.

digitalGauge1. CharacterType = CharacterTypes.SegmentSeven; 

 {% endhighlight %}





### To add multiple Digital Gauges

You can add Multiple Gauges in the preferred layout. The following code example explains how Multiple Gauges are added by using the LinearLayout.

{% highlight c# %}
 
  

   LinearLayout layout = new LinearLayout(this);

layout. Orientation = Orientation.Vertical;

layout.AddView(digitalGauge1);

layout.AddView(digitalGauge1);

layout.AddView(digitalGauge1);

layout.AddView(digitalGauge1);

layout. SetGravity(GravityFlags.Center);

 {% endhighlight %}



![http://help.syncfusion.com/ug/android/ImagesExt/image79_2.png](Create-your-first-Digital-Gauge-in-XamarinAndroid_images/Create-your-first-Digital-Gauge-in-XamarinAndroid_img3.png)

## Create your first Digital Gauge in Xamarin.iOS

This section provides a quick overview for working with the Essential Digital Gauge for Xamarin iOS. It guides you to the entire process of creating a real-world chart. You can learn how to create a Digital Gauge to display time similar to the digital clock with different Character types.

![](Create-your-first-Digital-Gauge-in-XamariniOS_images/Create-your-first-Digital-Gauge-in-XamariniOS_img1.png)



### Reference Essential Studio components in your solution

When the Essential Studio for Xamarin is installed, all the required assemblies can be found in the installation folders: {Syncfusion Installed location}\Essential Studio\13.1.0.21\lib


N> Assemblies are available in unzipped package location in Mac.

Add the following assembly references to the iOS project.

[iOS\Syncfusion.SfGauge.iOS.dll]

### Create a Digital Gauge

To develop an application with the XamariniOS Digital Gauge is simple. 

 Create an instance of the SfDigitalGauge.

{% highlight c# %}
 
  

   SFDigitalGauge digitalGauge1= new SFDigitalGauge ();

 {% endhighlight %}



### Add values to display

You can set the value for the gauge by using the Value in the DigitalGauge. It can be Alphabet, Numers, or Special Characters.

{% highlight c# %}
 
  

    NSDate date = new NSDate ();

NSString currentDateandTime = (NSString)date.ToString ();

//Sets the gauge value.

digitalGauge1.Value = currentDateandTime;

 {% endhighlight %}

 

The above code example explains how the values are assigned to the Digital Gauge. You can obtain the Time by using the SimpleDateFormat and that is assigned to the Digital Gauge. 

### Set the Digital Gauge customizations

The Digital Gauge is customized by setting the properties as explained in the following code example.

{% highlight c# %}
 
  

   digitalGauge1.CharacterHeight = 36;

digitalGauge1.CharacterWidth = 18;

digitalGauge1.SegmentWidth = 3;

digitalGauge1.VerticalPadding = 10;

digitalGauge1.CharacterType = SFDigitalGaugeCharacterType.SFDigitalGaugeCharacterTypeSegmentSeven;

digitalGauge1.StrokeType = SFDigitalGaugeStrokeType.SFDigitalGaugeStrokeTypeTriangleEdge;

digitalGauge1.DimmedSegmentAlpha = nfloat.Parse("0.11");

digitalGauge1.BackgroundColor = UIColor.FromRGB(248,248,248);

digitalGauge1.CharacterColor = UIColor.FromRGB(20,108,237);

digitalGauge1.DimmedSegmentColor = UIColor.FromRGB(20,108,237);

 {% endhighlight %}



### To add multiple Digital Gauge

You can add Multiple Gauges in the preferred layout. The following code example explains how Multiple Gauges are added by using the View.AddSubView.

{% highlight c# %}
 
  

   View.AddSubview (digitalGauge1);

View.AddSubview (digitalGauge2);

View.AddSubview (digitalGauge3);

View.AddSubview(digitalGauge4);

layout.AddView(digitalGauge1);

 {% endhighlight %}



![](Create-your-first-Digital-Gauge-in-XamariniOS_images/Create-your-first-Digital-Gauge-in-XamariniOS_img3.jpeg)




