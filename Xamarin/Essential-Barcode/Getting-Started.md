---
layout: post
title: Getting-Started
description: getting started
platform: xamarin
control: Control Name undefined
documentation: ug
---

# Getting Started

This section explains how to configure a Barcode for Xamarin Forms application. The following screenshot illustrates the final output of barcode on iOS, Android and Windows Phone devices. You can also download the entire source code of this demo [here](http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/BarcodeGettingStarted.zip).

![](Getting-Started_images/Getting-Started_img1.png)


To get started with Essential Barcode, go through the following steps.

## Referencing Essential Studio components in your solution

When you acquire Essential Studio components through the Xamarin Component Store interface from your IDE, after adding the components to your Xamarin.iOS, Xamarin.Android and WindowsPhone projects through the Component Manager, you have to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL Project in your solution. You can do this manually by adding the relevant PCL assembly references to your PCL project contained in the following path inside your solution folder: 

_Components/syncfusionessentialstudio-version/lib/pcl/_

Alternatively, when you download Essential Studio from Syncfusion.com or through the Xamarin Store web interface, add all the assembly references manually.  

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

_{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib_

_Example: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib_

Otherwise, after downloading through the Xamarin Store web interface, you can find all the required assemblies in the following folder:

_{download location}\syncfusionessentialstudio-version\lib_

Then, you can add the assembly references to the respective projects as follows.

### PCL project

XForms\Syncfusion.SfBarcode.XForms.dll  

### Android project

Android\Syncfusion.SfBarcode.Andriod.dll

Android\Syncfusion.SfBarcode.XForms.Andriod.dll 

### iOS project

iOS\Syncfusion.SfBarcode.iOS.dll   

iOS\Syncfusion.SfBarcode.XForms.iOS.dll

### Windows Phone project

WinPhone\Syncfusion.SfBarcode.WP8.dll

WinPhone\Syncfusion.SfBarcode.XForms.WinPhone.dll


_Note: Essential Barcode for Xamarin is compatible with Xamarin. Forms 1.3.4.6332._

Currently an additional step is required for Windows Phone and iOS projects. Create an instance of the Barcode custom renderer as mentioned.

Create an instance of SfBarcodeRenderer in MainPage constructor in Windows Phone project as follows.

{% highlight c# %}
 
    [C#]

public MainPage()

{

    new SfBarcodeRenderer();

    InitializeComponent();

}

 {% endhighlight %}



Similarly, create an instance of SfBarcodeRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

{% highlight c# %}
 
    [C#]

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

     new SfBarcodeRenderer ();

     return base.FinishedLaunching (app, options);

}

 {% endhighlight %}



## Configure the Barcode control

You can configure the Barcode control entirely in C# code or by using the XAML markup.

Here, the following steps illustrates how to create and configure a barcode.

1. Add reference to SFBarcode such as follows.

   ~~~ xml

        [XAML]

            xmlns:syncfusion="clr-namespace:Syncfusion.SfBarcode.XForms;assembly=Syncfusion.SfBarcode.XForms"
	
   ~~~
   {:.pretty-print }



   ~~~ cs

        [C#]

            using Syncfusion.SfBarcode.XForms;
	
   ~~~
   {:.pretty-print }





2. Create an instance of SfBarcode in XAML or code-behind using the reference of SfBarcode.

   ~~~ xml

        [XAML]

            <syncfusion:SfBarcode/>
	
   ~~~
   {:.pretty-print }



   ~~~ cs

        [C#]

            SfBarcode barcode = new SfBarcode();
	
   ~~~
   {:.pretty-print }





3. Then, you can assign the text that you want to encode.

   ~~~ xml

        [XAML]

            <syncfusion:SfBarcode Text="www.wikipedia.org"/>
	
   ~~~
   {:.pretty-print }



   ~~~ cs

        [C#]

            barcode.Text = "www.wikipedia.org";
	
   ~~~
   {:.pretty-print }





4. Specify the required symbology to encode the given text. By defau<, the given text is encoded using Code 39 symbology.

   ~~~ xml

        [XAML]

            <syncfusion:SfBarcode Text="www.wikipedia.org" Symbology="QRCode"/>
	
   ~~~
   {:.pretty-print }



   ~~~ cs

        [C#]

            barcode.Symbology = BarcodeSymbo<ype.QRCode;
	
   ~~~
   {:.pretty-print }





5. For customizing the barcode, initialize the settings of corresponding barcode symbology.

   ~~~ xml

        [XAML]

            <syncfusion:SfBarcode Text="www.wikipedia.org" Symbology="QRCode">

            <syncfusion:SfBarcode.SymbologySettings>

            <syncfusion:SfQRBarcodeSettings XDimension="6"/>

            </syncfusion:SfBarcode.SymbologySettings>

            </syncfusion:SfBarcode>
	
   ~~~
   {:.pretty-print }



   ~~~ cs

        [C#]

            SfQRBarcodeSettings settings = new SfQRBarcodeSettings();

            settings.XDimension = 6;

            barcode.SymbologySettings = settings;
	
   ~~~
   {:.pretty-print }





6. Finally, the barcode is generated as displayed in the following screenshot for the following code example.

   ~~~ xml

        [XAML]

        <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"

             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

             xmlns:syncfusion="clr-namespace:Syncfusion.SfBarcode.XForms;assembly=Syncfusion.SfBarcode.XForms"

             x:Class="BarcodeGettingStarted.SamplePage">

             <syncfusion:SfBarcode BackgroundColor="Gray" Text="www.wikipedia.org" Symbology="QRCode">

             <syncfusion:SfBarcode.SymbologySettings>

             <syncfusion:SfQRBarcodeSettings XDimension="6"/>

             </syncfusion:SfBarcode.SymbologySettings>

             </syncfusion:SfBarcode>

             </ContentPage>
	
   ~~~
   {:.pretty-print }



   ~~~ cs

        [C#]

        public SamplePage()

        {

            InitializeComponent();

            SfBarcode barcode = new SfBarcode();

            barcode.BackgroundColor = Color.Gray;

            barcode.Text = "www.wikipedia.org";

            barcode.Symbology = BarcodeSymbo<ype.QRCode;

            SfQRBarcodeSettings settings = new SfQRBarcodeSettings();

            settings.XDimension = 6;

            barcode.SymbologySettings = settings;

            this.Content = barcode;

        }
	
   ~~~
   {:.pretty-print }





   ![](Getting-Started_images/Getting-Started_img3.png)

## Create your first Barcode in Xamarin.Android

This section explains how to configure a Barcode for Xamarin.Android application by using C#. To get started with the Essential Barcode, refer to the following steps and in result, you get the output on Android devices as follows.

![](Create-your-first-Barcode-in-XamarinAndroid_images/Create-your-first-Barcode-in-XamarinAndroid_img1.png)


### Reference Essential Studio components in your solution

After installing the Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Installed location}\Essential Studio\12.4.0.24\lib


_Note: Assemblies are available__in unzipped package location in Mac_

Add the following assembly references to the Android project,

[android\Syncfusion.SfBarcode.Andriod.dll]

### Configure the Barcode control

The following steps explain how to create and configure a Barcode.

1. Add reference to the SfBarcode as follows.

   ~~~ cs

        [C#]

            using Com.Syncfusion.Barcode
	
   ~~~
   {:.pretty-print }





2. Create a SfBarcode instance in Main Activity and set the sfBarcode as a ContentView in onCreate() overridden method.

   ~~~ cs

        [C#]

            public class MainActivity : Activity

            {

            protected override void OnCreate(Bundle bundle)

            {

                base.OnCreate(bundle);

                SfBarcode sfBarcode = new SfBarcode(this);

                SetContentView(sfBarcode);

            }
	
   ~~~
   {:.pretty-print }





3. Then you can set the text that you want to encode.

   ~~~ cs

        [C#]

            sfBarcode.Text = "http://www.wikipedia.org";
	
   ~~~
   {:.pretty-print }





4. Set the required symbology to encode the given text. By default, the given text is encoded by using the Code 39 symbology.

   ~~~ cs

        [C#]

            sfBarcode.Symbology = BarcodeSymbolType.QRBarcode;
	
   ~~~
   {:.pretty-print }





5. To customize the Barcode, initialize the settings of the corresponding Barcode symbology.

   ~~~ cs

        [C#]

            QRBarcodeSettings setting = new QRBarcodeSettings();

            setting.XDimension = 15;

            sfBarcode.SymbologySettings = setting;
	
   ~~~
   {:.pretty-print }





6. Finally, the Barcode is generated as shown in the screenshot for the following code example.

   ~~~ cs

        [C#]

            public class MainActivity : Activity

            {

            protected override void OnCreate(Bundle bundle)

            {

                base.OnCreate(bundle);

                SfBarcode sfBarcode = new SfBarcode(this);

                sfBarcode.Text = "http://www.wikipedia.org";

                sfBarcode.Symbology = BarcodeSymbolType.QRBarcode;

                QRBarcodeSettings setting = new QRBarcodeSettings();

                setting.XDimension = 15;

                sfBarcode.SymbologySettings = setting;

                SetContentView(sfBarcode);

            }

            }
	
   ~~~
   {:.pretty-print }





   ![](Create-your-first-Barcode-in-XamarinAndroid_images/Create-your-first-Barcode-in-XamarinAndroid_img3.png)



## Create your first Barcode in Xamarin.iOS

This section explains how to configure a Barcode for Xamarin.iOS application by using C#. To get started with the Essential Barcode, refer to the following steps and in result, you get the output on iOS devices as follows.

![](Create-your-first-Barcode-in-XamariniOS_images/Create-your-first-Barcode-in-XamariniOS_img1.png)


### Add framework reference to the project

#### Reference Essential Studio Components in your Solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio\{version number}\lib\iOS


_Note: Assemblies are available in unzipped package location in Mac._

From the specified folder, the assembly reference of the SfBarcode that is, Syncfusion.SfBarcode.iOS.dll is added to the Xamarin.iOS project.

### Configure the Barcode control

The following steps explain how to create and configure a Barcode.

1. Add reference to the SfBarcode in view controller as follows

   ~~~ cs

        [C#]

            using Syncfusion.SfBarcode.iOS;
	
   ~~~
   {:.pretty-print }



2. Then, create an instance of the SfBarcode and add it as sub view in viewDidLoad override function.

   ~~~ cs

        [C#]

            public override void ViewDidLoad ()

            {
                base.ViewDidLoad ();

                SFBarcode barcode = new SFBarcode();

                this.View.AddSubview (barcode);

            }
	
   ~~~
   {:.pretty-print }


3. Then you can assign the text that you want to encode.

   ~~~ cs

        [C#]

            barcode.Text = (NSString)"www.wikipedia.org";
	
   ~~~
   {:.pretty-print }



4. Specify the required symbology to encode the given text. By default, the given text is encoded by using the Code 39 symbology.

   ~~~ cs

        [Swift]

            barcode.Symbology = SFBarcodeSymbolType.SFBarcodeSymbolTypeQRCode;
	
   ~~~
   {:.pretty-print }




5. To customize the Barcode, initialize the settings of the corresponding Barcode symbology.

   ~~~ cs

        [C#]

            SFQRBarcodeSettings settings = new SFQRBarcodeSettings ();

            settings.XDimension = 6;

            barcode.SymbologySettings = settings;
	
   ~~~
   {:.pretty-print }







6. Finally, the Barcode is generated as shown in the screenshot for the following code example.

   ~~~ cs

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
	
   ~~~
   {:.pretty-print }





![](Create-your-first-Barcode-in-XamariniOS_images/Create-your-first-Barcode-in-XamariniOS_img3.png)