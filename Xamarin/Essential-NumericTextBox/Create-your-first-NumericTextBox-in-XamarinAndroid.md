---
layout: post
title: Create-your-first-NumericTextBox-in-XamarinAndroid
description: create your first numerictextbox in xamarin.android
platform: ios
control: Control Name undefined
documentation: ug
---

#### Create your first NumericTextBox in Xamarin.Android

This section encompasses how to create the NumericTextBox that lets you to enter values in an efficient way. You can also display numbers in the format of its mentioned culture. In this instance, how to create a NumericTextBox and to use its several features have been demonstrated.



Add Syncfusion assembly reference

After installing the Essential StudioforXamarin, you can find all the required assemblies in the following installed folders,

{Syncfusion Installed location}\Essential Studio\{version number}\lib

![ttp://help.syncfusion.com/ug/android/ImagesExt/image81_8.png](Create-your-first-NumericTextBox-in-XamarinAndroid_images/Create-your-first-NumericTextBox-in-XamarinAndroid_img1.png)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac._

 Add the following assembly references to the Xamarin project.



android\Syncfusion.SfNumericTextBox.Andriod.dll





![](Create-your-first-NumericTextBox-in-XamarinAndroid_images/Create-your-first-NumericTextBox-in-XamarinAndroid_img2.png)
{:.image }




Create a NumericTextBox

To develop an application with the Android NumericTextBox is simple. The following steps explain how to create and configure its properties.

Create an instance for the SfNumericTextBox in the constructor and set that SfNumericTextBox as content view of Activity. 

[C#]



SfNumericTextBox numtext=new SfNumericTextBox(this);

SetContentView(numtext);

Configure the NumericTextBox

You can set the initial value and numberformat for the NumericTextBox by using the value and formatString properties in the NumericTextBox. 

[C#]

numtext.Value=123.45;

numtext.FormatString=”n”;

numtext.MaximumNumberDecimalDigits=2;

The above code example illustrates the value and formatstring of the NumericTextBox. The MaximumNumberDecimalDigits can be specified to determine the digits after the decimal.



Adding ParsingMode

Value of the NumericTextBox gets parsed based on the ParsingMode property. ParsingMode is of type Parsers that is the enum of Double and Decimal.

[C#]

numtext.Value=123.45;

numtext.ParsingMode=Parsers.Decimal



![](Create-your-first-NumericTextBox-in-XamarinAndroid_images/Create-your-first-NumericTextBox-in-XamarinAndroid_img3.png)
{:.image }




![](Create-your-first-NumericTextBox-in-XamarinAndroid_images/Create-your-first-NumericTextBox-in-XamarinAndroid_img4.png)
{:.image }




