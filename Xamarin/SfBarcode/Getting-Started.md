---

layout: post
title: Syncfusion SfBarcode control Getting Started for Xamarin.Forms
description: A quick tour to initial users on Syncfusion SfBarcode control for Xamarin.Forms platform
platform: xamarin
control: SfBarcode
documentation: ug

---

# Getting Started 

This section explains how to configure a Barcode for Xamarin.Forms application. The following screenshot illustrates the final output of barcode on iOS, Android and Windows Phone devices.

![Overview of SfBarcode](Getting-Started_images/getting-started/getting-started.png)

To get started with Essential Barcode, go through the following steps.

## Adding SfBarcode reference

You can add SfBarcode reference using one of the following methods:

**Method 1: Adding SfBarcode reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfBarcode to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfBarCode](https://www.nuget.org/packages/Syncfusion.Xamarin.SfBarCode), and then install it.

![Adding SfBarcode reference from nuget](Getting-Started_images/getting-started/Adding SfBarcode reference.png)

N> Install the same version of SfBarcode NuGet in all the projects.

**Method 2: Adding SfBarcode reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfBarcode control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfBarcode assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfBarcode.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfBarcode.Android.dll<br/>Syncfusion.SfBarcode.XForms.Android.dll<br/>Syncfusion.SfBarcode.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfBarcode.iOS.dll<br/>Syncfusion.SfBarcode.XForms.iOS.dll<br/>Syncfusion.SfBarcode.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfBarcode.UWP.dll<br/>Syncfusion.SfBarcode.XForms.UWP.dll<br/>Syncfusion.SfBarcode.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

N> If you are adding the references from toolbox, this step is not needed.

Currently an additional step is required for Windows Phone and iOS projects. Create an instance of the Barcode custom renderer as mentioned.

Create an instance of `SfBarcodeRenderer` in MainPage constructor in of the Windows Phone project as shown

{% highlight c# %}

    public MainPage ()
    {
    ...
    new SfBarcodeRenderer();
    InitializeComponent();
    ...
    }

{% endhighlight %}

Similarly, create an instance of `SfBarcodeRenderer` in Finished Launching overridden method of `AppDelegate` class in iOS Project as follows.

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

1. Add reference to SfBarcode such as follows.


{% tabs %}
{% highlight xaml %}

    xmlns:syncfusion="clr-namespace:Syncfusion.SfBarcode.XForms;assembly=Syncfusion.SfBarcode.XForms"

{% endhighlight %}

{% highlight c# %}
    
   
    using Syncfusion.SfBarcode.XForms;
    
{% endhighlight %}
{% endtabs %}

2. Create an instance of `SfBarcode` in XAML or code-behind using the reference of `SfBarcode`.

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

4. Specify the required `Symbology` to encode the given text. By default, the given text is encoded using Code 39 `Symbology`.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBarcode Text="http://www.syncfusion.com" Symbology="QRCode"/>
{% endhighlight %}

{% highlight c# %}
    
    barcode.Symbology = BarcodeSymbolType.QRCode;

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

    <syncfusion:QRBarcodeSettings XDimension="6"/> 

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

    barcode.Symbology = BarcodeSymbolType.QRCode;

    QRBarcodeSettings settings = new QRBarcodeSettings(); 

    settings.XDimension = 6; 

    barcode.SymbologySettings = settings; 

    this.Content = barcode; 

    }

{% endhighlight %}
{% endtabs %}

![Final output of SfBarcode](Getting-Started_images/barcode/barcode.png)