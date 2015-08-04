---
layout: post
title: Create-your-first-RangeSlider-in-XamariniOS
description: create your first rangeslider in xamarin.ios
platform: ios
control: Control Name undefined
documentation: ug
---

#### Create your first RangeSlider in Xamarin.iOS

This section encompasses how to create the RangeSlider that lets you to choose values over a high interactive way. You can also display special characters in different character types. In this instance, how to create a RangeSlider and to use its several features are demonstrated.

![](Create-your-first-RangeSlider-in-XamariniOS_images/Create-your-first-RangeSlider-in-XamariniOS_img1.png)
{:.image }


Reference Essential Studio Components in your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the following installated folders:



{Syncfusion Installed location}\Essential Studio\{version number}\lib



> ![](Create-your-first-RangeSlider-in-XamariniOS_images/Create-your-first-RangeSlider-in-XamariniOS_img2.png)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac._

Add the following assembly references to the iOS project.



iOS\Syncfusion.SfRangeSlider.iOS.dll



Create a Rangeslider

To develop an application with the iOS RangeSlider is simple. The following steps explain how to create and configure its properties.

Create an instance for SfRangeSlider and add the SfRangeSlider as subview in the viewdidload override method.

//C#



public override void ViewDidLoad ()

{
    base.ViewDidLoad ();

    SFRangeSlider rangeSlider= new SFRangeSlider ();

    View.AddSubview (rangeSlider);



Add values and scale

You can set the minimum and maximum values for the slider by using the minimum and maximum in the Rangeslider. It can be Numerical values.

//C#



  rangeSlider.Maximum = 12;
  rangeSlider.Minimum = 0;
  rangeSlider.RangeStart = 0;
  rangeSlider.RangeEnd = 12; 



The above code example illustrates the Minimum and Maximum value for the Slider. Similarly, RangeStart and RangeEnd is used to set the start range and end range values when you use dual thumb. The ShowRange property is used to switch between single thumb and double thumb.

Add Ticks and Labels for the RangeSlider

The ticks can be set by using the TickFrequency and TickPlacement. Similarly, value labels can be set by using the ShowValueLabel property to true. The position of label can be varied by the LabelPlacement property.

//C#



  rangeSlider1.TickPlacement = SFTickPlacement.SFTickPlacementBottomRight;
  rangeSlider1.TickFrequency = 2;
  rangeSlider1.ValuePlacement = SFValuePlacement.SFValuePlacementBottomRight;



The above code example illustrates on setting the Tick and ValuePlcaements. The TickFrequency determines the interval between the ticks. 

Add Snapping type for RangeSlider

The movement of the thumb can be varied in different ways. This is achieved by setting the SnapsTo property.

//C#



rangeSlider.SnapsTo = SFSnapsTo.SFSnapsToTicks;

The movement of the thumb is based on Ticks / StepFrequency / none. When it is set to Tick, the Thumb is moved to next / nearby tick and on setting to none, the Thumb is moved independently.

![](Create-your-first-RangeSlider-in-XamariniOS_images/Create-your-first-RangeSlider-in-XamariniOS_img3.png)
{:.image }


