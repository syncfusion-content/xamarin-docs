---
layout: post
title: Getting Started | SfBusyIndicator |Xamarin | Syncfusion
description: getting started
platform: xamarin
control: SfBusyIndicator
documentation: ug
---

# Getting Started

This section provides a quick overview for working with Essential BusyIndicator for Xamarin.Forms.

## Add Syncfusion assembly reference

Add the required Syncfusionassembly references to the respective projects as follows. Refer to the following installed location for the required assemblies.

{Syncfusion Installed location}\Essential Studio\12.4.0.34\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.4.0.34\lib

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


N> Essential BusyIndicator for Xamarin is compatible with Xamarin Forms 1.3.

An additional step is required for Windows Phone and iOS projects. Create an instance of the BusyIndicator custom renderer as follows.

Create an instance of the SfBusyIndicatorRenderer in MainPage constructor in Windows Phone project as follows.

{% highlight c# %}  

public MainPage()

{

new SfBusyIndicatorRenderer ();

        ...    

}

 {% endhighlight %}


Create an instance of the SfBusyIndicatorRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows

{% highlight c# %}
    
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

{% tabs %}  

{% highlight c# %} 

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

// Use this in App.CS source.

<?xml version="1.0" encoding="UTF-8"?>

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
	xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"           
x:Class="BusyIndicatorGettingStarted.BusyIndicatorGettingStarted" 
	BackgroundColor="White"   
xmlns:syncfusion="clr-namespace:Syncfusion.SfBusyIndicator.XForms;
	assembly=Syncfusion.SfBusyIndicator.XForms"  	         
xmlns:picker="clr-namespace:BusyIndicatorGettingStarted;
	assembly=BusyIndicatorGettingStarted">
	
<ContentPage.Content> x:Class="BusyIndicatorGettingStarted.Sample">
	<ContentPage.Content>
		<syncfusion:SfBusyIndicator     
	</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% endtabs %}  



### Configure the BusyIndicator Properties

Add the BusyIndicator properties in your application.

{% tabs %}  

{% highlight c# %}    

SfBusyIndicator sfbusyindicator = new SfBusyIndicator();

sfbusyindicator.AnimationType = AnimationTypes.Battery;

sfbusyindicator.ViewBoxWidth = 150;

sfbusyindicator.ViewBoxHeight = 150;

sfbusyindicator.BackgroundColor = Color.White;

{% endhighlight %}



{% highlight xml %}   

    <syncfusion:SfBusyIndicator x:Name="sfbusyindicator" BackgroundColor="White" ViewBoxHeight="150" ViewBoxWidth="150" AnimationType="Ball"/>

{% endhighlight %}


{% endtabs %}  


The following screenshot illustrates the output.

![](Getting-Started_images/img2.png)

## Create your first BusyIndicator in Xamarin.Android

This section provides a quick overview to work with the BusyIndicator in the Xamarin Studio. You can also set the requiredAnimationType to BusyIndicator and customize it according to your requirements. This example explains how to create theBusyIndicator with different AnimationTypes.



![](Create-your-first-BusyIndicator-in-XamarinAndroid_images/img1.png)


### Reference Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\13.1.0.21\lib

 
N> Assemblies are available in unzipped package location in Mac

### Add the following assembly references to the Xamarin project.

 [android\Syncfusion.SfBusyIndicator.Andriod.dll]

To develop an application with the Xamarin BusyIndicator is simple. The following steps explain how to create and configure its properties.

Create an instance for the SfBusyIndicator in the constructor and set that BusyIndicator as content view of Activity.

{% highlight c# %}   

SfBusyIndicator sfBusyIndicator = new SfBusyIndicator(this);

setContentView(sfBusyIndicator);

{% endhighlight %}



### Set the AnimationType to BusyIndicator

You can set the AnimationType to the BusyIndicator by using the property Animationtype and choose among 13 predefined animation types.

{% highlight c# %}    

SfBusyIndicator busyIndicator = new SfBusyIndicato(this);

busyIndicator.AnimationType=AnimationTypes.Battery;

{% endhighlight %}

   

### Set BusyIndicator Customizations

The BusyIndicator is customized by setting the properties as explained in the following code example.

{% highlight c# %}   
 
SfBusyIndicator busyIndicator = new SfBusyIndicator (this);

busyIndicator.AnimationType=AnimationTypes.Battery;

busyIndicator.ViewBoxHeight=100;

busyIndicator.ViewBoxWidth=100;

busyIndicator.TextColor=Color.RED;

busyIndicator.Title=“Loading”;

setContentView(busyIndicator);

{% endhighlight %}

## Create your first BusyIndicator in Xamarin.iOS

This section provides a quick overview to work with the BusyIndicator in Xamarin.iOS. You can also set the required AnimationType to the BusyIndicator and customize it according to your requirements. This example explains how to create a BusyIndicator with different AnimationTypes.



![](Create-your-first-BusyIndicator-in-XamariniOS_images/img1.png)



### Reference Essential Studio Components in your Solution

After installing the Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:



{Syncfusion Installed location}\Essential Studio\{version number}\lib

N> Assemblies are available in unzipped package location in Mac.

You can add the following assembly references to the iOS project.

 [iOS\Syncfusion.SfBusyIndicator.iOS.dll]

### Create a BusyIndicator

To develop an application with the iOS BusyIndicator is simple. Following steps explain how to create and configure its elements,

1.Create a BusyIndicator object and add BusyIndicator as subview in the viewdidload override method.

2.You can create a BusyIndicator object by using the following code example.

{% highlight c# %}

public override void ViewDidLoad ()
{
	base.ViewDidLoad ();

    SFBusyIndicator busyIndicator = new SFBusyIndicator ();

    View.AddSubview (busyIndicator);

{% endhighlight %}







### Set the Animation Type to BusyIndicator

You can set the AnimationType to the BusyIndicator by using the property Animationtype and choose among 13 predefined animation types. 

{% highlight c# %}  

SFBusyIndicator busyIndicator = new SFBusyIndicator ();

busyIndicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBall;

{% endhighlight %}





### Set BusyIndicator Customizations

BusyIndicator can be customized by setting the properties as explained in the following code example.

{% highlight c# %}
 
SFBusyIndicator busyIndicator = new SFBusyIndicator ();

busyIndicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBall;

busyIndicator.ViewBoxWidth = 100;

busyIndicator.ViewBoxHeight = 100;

busyIndicator.Foreground = UIColor.Red;

busyIndicator.Title = "Loading.....";

View.AddSubview (busyIndicator);

{% endhighlight %}

 



