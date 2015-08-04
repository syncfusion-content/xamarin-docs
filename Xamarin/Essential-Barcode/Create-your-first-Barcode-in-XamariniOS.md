---
layout: post
title: Create-your-first-Barcode-in-XamariniOS
description: create your first barcode in xamarin.ios
platform: ios
control: Control Name undefined
documentation: ug
---

#### Create your first Barcode in Xamarin.iOS

This section explains how to configure a Barcode for Xamarin.iOS application by using C#. To get started with the Essential Barcode, refer to the following steps and in result, you get the output on iOS devices as follows.

![](Create-your-first-Barcode-in-XamariniOS_images/Create-your-first-Barcode-in-XamariniOS_img1.png)
{:.image }


Add framework reference to the project

Reference Essential Studio Components in your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio\{version number}\lib\iOS

![](Create-your-first-Barcode-in-XamariniOS_images/Create-your-first-Barcode-in-XamariniOS_img2.png)
{:.image }
_Note: Assemblies are available in unzipped package location in Mac._

From the specified folder, the assembly reference of the SfBarcode that is, Syncfusion.SfBarcode.iOS.dll is added to the Xamarin.iOS project.

Configure the Barcode control

The following steps explain how to create and configure a Barcode.

1. Add reference to the SfBarcode in view controller as follows

[C#]

using Syncfusion.SfBarcode.iOS;



2. Then, create an instance of the SfBarcode and add it as sub view in viewDidLoad override function.

[C#]

public override void ViewDidLoad ()

{
       base.ViewDidLoad ();

       SFBarcode barcode = new SFBarcode();

       this.View.AddSubview (barcode);

}



3. Then you can assign the text that you want to encode.

[C#]

barcode.Text = (NSString)"www.wikipedia.org";



4. Specify the required symbology to encode the given text. By default, the given text is encoded by using the Code 39 symbology.

[Swift]

barcode.Symbology = SFBarcodeSymbolType.SFBarcodeSymbolTypeQRCode;



5. To customize the Barcode, initialize the settings of the corresponding Barcode symbology.

[C#]

SFQRBarcodeSettings settings = new SFQRBarcodeSettings ();

settings.XDimension = 6;

barcode.SymbologySettings = settings;



6. Finally, the Barcode is generated as shown in the screenshot for the following code example.

[C#]

public override void ViewDidLoad ()

{

       base.ViewDidLoad ();

       SFBarcode barcode = new SFBarcode();

       barcode.Text = (NSString)"www.wikipedia.org";

       barcode.Symbology = SFBarcodeSymbolType.SFBarcodeSymbolTypeQRCode;

       SFQRBarcodeSettings settings = new SFQRBarcodeSettings ();

       settings.XDimension = 6;

       barcode.SymbologySettings = settings;

       this.View.AddSubview (barcode);

}



![](Create-your-first-Barcode-in-XamariniOS_images/Create-your-first-Barcode-in-XamariniOS_img3.png)
{:.image }


