---

layout: post
title: Syncfusion SfBarcode control Getting Started for Xamarin.Forms
description: A quick tour to initial users on Syncfusion SfBarcode control for Xamarin.Forms platform
platform: Xamarin.Forms
control: SfBarcode
documentation: ug

---

# GETTING STARTED 

This section explains how to configure a Barcode for Xamarin Forms application. The following screenshot illustrates the final output of barcode on iOS, Android and Windows Phone devices.

![](getting-started_images/getting-started/getting-started.png)

_Barcode_ _control_ _rendering_ _2D_ _bar_ _code_

To get started with Essential Barcode, go through the following steps.

## Referencing Essential Studio components in your solution

When you acquire Essential Studio components through the Xamarin Component Store interface from your IDE, after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component Manager, you have to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL Project in your solution. You can do this manually by adding the relevant PCL assembly references to your PCL project contained in the following path inside your solution folder:

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib

Example: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib

Otherwise, after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as follows

### PCL project

pcl\Syncfusion.SfBarcode.XForms.dll

### Android project

android\Syncfusion.SfBarcode.Android.dll

android\Syncfusion.SfBarcode.XForms.Android.dll

### iOS (Classic) project

iOS\Syncfusion.SfBarcode.iOS.dll

iOS\Syncfusion.SfBarcode.XForms.iOS.dll

iOS\Syncfusion.SfBarcode.XForms.dll

### iOS(Unified) project

ios-unified\Syncfusion.SfBarcode.iOS.dll

ios-unified\Syncfusion.SfBarcode.XForms.iOS.dll

ios-unified\Syncfusion.SfBarcode.XForms.dll

### Windows Phone project

wp8\Syncfusion.SfBarcode.WP.dll

wp8\Syncfusion.SfBarcode.XForms.WinPhone.dll

>**NOTE**
Essential Barcode for Xamarin is compatible with Xamarin. Forms 1.3.4.6332.

Currently an additional step is required for Windows Phone and iOS projects. Create an instance of the Barcode custom renderer as mentioned.

Create an instance of SfBarcodeRenderer in MainPage constructor in of the Windows Phone project as shown

{% highlight c# %}

    public MainPage ()
    {
    ...
    new SfBarcodeRenderer();
    Initializecomponent();
    ...
    }

{% endhighlight %}

Similarly, create an instance of SfBarcodeRenderer in Finished Launching overridden method of AppDelegate class in iOS Project as follows.

{% highlight c# %}
    
    public override bool Finished Launching (UIApplication app, NSDictionary options)
    {
    ... 
    new SfBarcodeRenderer ();
    return base.FinishedLaunching(app, options);
    ...

{% endhighlight %}

## Configure the Barcode control

You can configure the Barcode control entirely in C# code or by using the XAML markup.

Here, the following steps illustrates how to create and configure a barcode.

1. Add reference to SFBarcode such as follows.


{% tabs %}
{% highlight xaml %}

    xmlns:syncfusion="clr-namespace:Syncfusion.SfBarcode.XForms;assembly=Syncfusion.SfBarcode.XForms"

{% endhighlight %}

{% highlight c# %}
    
   
    using Syncfusion.SfBarcode.XForms;
    
{% endhighlight %}
{% endtabs %}

2. Create an instance of SfBarcode in XAML or code-behind using the reference of SfBarcode.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBarcode/>

{% endhighlight %}

{% highlight c# %}

    SfBarcode barcode = new SfBarcode();
    
{% endhighlight %}
{% endtabs %}

3. Then, you can assign the text that you want to encode.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBarcode Text="http://www.syncfusion.com"/>

{% endhighlight %}

{% highlight c# %}

    barcode.Text = " http://www.syncfusion.com ";

{% endhighlight %}
{% endtabs %}

4. Specify the required symbology to encode the given text. By default<, the given text is encoded using Code 39 symbology.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBarcode Text="http://www.syncfusion.com" Symbology="QRCode"/>
{% endhighlight %}

{% highlight c# %}
    
    barcode.Symbology = BarcodeSymboltype.QRCode;

{% endhighlight %}
{% endtabs %}

5. For customizing the barcode, initialize the settings of corresponding barcode symbology.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBarcode Text="http://www.syncfusion.com" Symbology="QRCode">

    <syncfusion:SfBarcode.SymbologySettings> 

    <Syncfusion:SfQRBarcodeSettings XDimension="6"/> 

    </syncfusion:SfBarcode.SymbologySettings> 

    </syncfusion:SfBarcode>

{% endhighlight %}

{% highlight c# %}

    SfQRBarcodeSettings settings = new SfQRBarcodeSettings(); 

    settings.XDimension = 6; 

    barcode.SymbologySettings = settings;

{% endhighlight %}
{% endtabs %}

6. Finally, the barcode is generated as displayed in the following screenshot for the following code example.

{% tabs %}
{% highlight xaml %}

    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"

    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

    xmlns:syncfusion="clr-namespace:Syncfusion.SfBarcode.XForms;assembly=Syncfusion.SfBarcode.XForms"

    x:Class="BarcodeGettingStarted.SamplePage"> 

    <syncfusion:SfBarcode BackgroundColor="Gray" Text="www.wikipedia.org" Symbology="QRCode">

    <syncfusion:SfBarcode.SymbologySettings>

    <syncfusion:QRcodeSettings XDimension="6"/> 

    </syncfusion:SfBarcode.SymbologySettings>

    </syncfusion:SfBarcode> </ContentPage>
{% endhighlight %}

{% highlight c# %}

    public SamplePage() 

    { 

    InitializeComponent(); 

    SfBarcode barcode = new SfBarcode(); 

    barcode.BackgroundColor = Color.Gray; 

    barcode.Text = "http://www.syncfusion.com"; 

    barcode.Symbology = BarcodeSymboltype.QRCode;

    QRcodeSettings settings = new QRcodeSettings(); 

    settings.XDimension = 6; 

    barcode.SymbologySettings = settings; 

    this.Content = barcode; 

    }

{% endhighlight %}
{% endtabs %}

![](getting-started_images/barcode/barcode.png)