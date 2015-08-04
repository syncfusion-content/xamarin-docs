---
layout: post
title: Create-your-first-BusyIndicator-in-XamariniOS
description: create your first busyindicator in xamarin.ios
platform: xamarin
control: Control Name undefined
documentation: ug
---

#### Create your first BusyIndicator in Xamarin.iOS

This section provides a quick overview to work with the BusyIndicator in Xamarin.iOS. You can also set the required AnimationType to the BusyIndicator and customize it according to your requirements. This example explains how to create a BusyIndicator with different AnimationTypes.



![](Create-your-first-BusyIndicator-in-XamariniOS_images/Create-your-first-BusyIndicator-in-XamariniOS_img1.png)
{:.image }



Reference Essential Studio Components in your Solution

After installing the Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:



{Syncfusion Installed location}\Essential Studio\{version number}\lib

> ![](Create-your-first-BusyIndicator-in-XamariniOS_images/Create-your-first-BusyIndicator-in-XamariniOS_img2.png)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac._

You can add the following assembly references to the iOS project.

 iOS\Syncfusion.SfBusyIndicator.iOS.dll

Create a BusyIndicator

To develop an application with the iOS BusyIndicator is simple. Following steps explain how to create and configure its elements,

1. Create a BusyIndicator object and add BusyIndicator as subview in the viewdidload override method.
2. You can create a BusyIndicator object by using the following code example.

//C#



public override void ViewDidLoad ()
        {
            base.ViewDidLoad ();

            SFBusyIndicator busyIndicator = new SFBusyIndicator ();

            View.AddSubview (busyIndicator);



Set the Animation Type to BusyIndicator

You can set the AnimationType to the BusyIndicator by using the property Animationtype and choose among 13 predefined animation types. 

//C#

SFBusyIndicator busyIndicator = new SFBusyIndicator ();

busyIndicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBall;



Set BusyIndicator Customizations

BusyIndicator can be customized by setting the properties as explained in the following code example.

//C#

SFBusyIndicator busyIndicator = new SFBusyIndicator ();

busyIndicator.AnimationType = SFBusyIndicatorAnimationType.SFBusyIndicatorAnimationTypeBall;

busyIndicator.ViewBoxWidth = 100;
busyIndicator.ViewBoxHeight = 100;

busyIndicator.Foreground = UIColor.Red;

busyIndicator.Title = "Loading.....";
View.AddSubview (busyIndicator);





