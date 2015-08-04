---
layout: post
title: Create-your-first-NumericTextBox-in-XamariniOS
description: create your first numerictextbox in xamarin.ios
platform: xamarin
control: Control Name undefined
documentation: ug
---

#### Create your first NumericTextBox in Xamarin.iOS

This section encompasses how to create the NumericTextBox that lets you enter values in an efficient way. You can also display numbers in the format of its mentioned culture. In this instance, how to create a NumericTextBox and to use its several features have been demonstrated.

Add Syncfusion assembly reference

After installing Essential Studio for Xamarin, you can find all the required assemblies in the following installed folders:

 {Syncfusion Installed location}\Essential Studio\{version number}\lib

![http://help.syncfusion.com/ug/xamarin/ImagesExt/image283_5.png](Create-your-first-NumericTextBox-in-XamariniOS_images/Create-your-first-NumericTextBox-in-XamariniOS_img1.png)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac._

Add the following assembly references to the iOS project.

 iOS\Syncfusion.SfNumericTextBox.iOS.dll

Creating a NumericTextBox

To develop an application with the iOS NumericTextBox is simple. The following steps explain how to create and configure its properties.

Create an instance for the SfNumericTextBox in the constructor and set that SfNumericTextBox as the content view of Activity. 



[C#]



 public override void ViewDidLoad ()

{

  base.ViewDidLoad   ();

  SFNumericTextBox numericTextBox1;

  numericTextBox1.Frame = new CGRect (200, 120, 100, 40)]

  }



Configure the NumericTextBox

You can set the initial value and numberformat for the NumericTextBox by using the value and formatString properties in the NumericTextBox. 

[C#]

numericTextBox1.Value = 1000;

numericTextBox1.FormatString=”n”;

numericTextBox1.MaximumNumberDecimalDigits = 2;



The above code example illustrates the value and formatstring of the NumericTextBox. The MaximumNumberDecimalDigits can be specified to determine the digits after the decimal.



![](Create-your-first-NumericTextBox-in-XamariniOS_images/Create-your-first-NumericTextBox-in-XamariniOS_img2.png)
{:.image }




Adding ParsingMode

Value of the NumericTextBox gets parsed based on the ParsingMode property. ParsingMode is of type Parsers that is the enum of Double and Decimal.

[C#]



numericTextBox1.ParserMode = SFNumericTextBoxParsers.Decimal;



![](Create-your-first-NumericTextBox-in-XamariniOS_images/Create-your-first-NumericTextBox-in-XamariniOS_img3.png)
{:.image }


![](Create-your-first-NumericTextBox-in-XamariniOS_images/Create-your-first-NumericTextBox-in-XamariniOS_img4.png)
{:.image }




