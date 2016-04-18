---

layout: post
title: Syncfusion SfCircularGauge control for Xamarin.Forms
description:  A quick tour to initial users on Syncfusion SfCircularGauge control for Xamarin.Forms Platform
platform: xamarin
control: SfCircularGauge
documentation: ug

---


# GETTING STARTED 

This section explains you the steps required to configure the **SfCircularGauge** and also explains the steps to add basic elements of **SfCircularGauge** through various API’s available within it.

## Referencing Essential Studio components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib

E.g.: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below

### PCL project

pcl\Syncfusion.SfGauge.XForms.dll

### Android project

android\Syncfusion.SfGauge.Android.dll

android\Syncfusion.SfGauge.XForms.Android.dll

android\Syncfusion.SfGauge.XForms.dll

### iOS (Classic) project

iOS\Syncfusion.SfGauge.iOS.dll

iOS\Syncfusion.SfGauge.XForms.iOS.dll

iOS \Syncfusion.SfGauge.XForms.dll

### iOS(Unified) project

iOS-unified\Syncfusion.SfGauge.iOS.dll

iOS-unified\Syncfusion.SfGauge.XForms.iOS.dll

iOS-unified\Syncfusion.SfGauge.XForms.dll

### Windows Phone project

wp81\Syncfusion.SfGauge.WP.dll

wp81\Syncfusion.SfGauge.XForms.WinPhone.dll

wp81\ Syncfusion.SfGauge.XForms.dll

Currently an additional step is required for Windows Phone and iOS projects. We need to create an instance of the chart custom renderer as shown below.

Create an instance of `SfGaugeRenderer` in MainPage constructor in of the Windows Phone project as shown.
{% highlight c# %}

    public MainPage ()
    {
    …
    new SfGaugeRenderer();
    ...
    }
{% endhighlight %}

Create an instance of `SfGaugeRenderer` in Finished Launching overridden method of App Delegate class in iOS Project as shown below

{% highlight c# %}

    public override bool Finished Launching (UIApplication app, NSDictionary options)
    {
    ...
    new SfGaugeRenderer();
    ...
    }
{% endhighlight %}


## Initializing Gauge 

The SfGauge control is configured entirely in C# code. 
{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge ();
    this.Content = circulargauge;

{% endhighlight %}

## Adding Header

You can assign a unique header to **SfCircularGauge** by making use of **Header** property and you can positioned it wherever you want using **Position** and **HeaderAlignment** property.

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge(); 
    Header header = new Header();
    header.Text = "Speedmeter";
    header.TextSize = 20;
    header.Position = Device.OnPlatform(iOS: new Point(.3, .7), Android:new Point(0.38, 0.7), WinPhone: new Point(0.38, 0.7));
    header.ForegroundColor = Color.Gray;
    circularGauge.Headers.Add(header); 
    this.content = circularGauge;
    
{% endhighlight %}

## Configuring Scales

You can configure the **CircularScale** elements by making use of following API’s available in `SfCircularGage`.

They are:

* StartAngle
* SweepAngle
* StartValue
* EndValue
* Interval
* RimThickness
* RimColor

{% highlight c# %}

    Scale scale = new Scale();
    scale.StartValue = 0; 
    scale.EndValue = 100;
    scale.Interval = 10;
    scale.StartAngle = 135;
    scale.SweepAngle = 270;
    scale.RimThickness =  20;
    scale.RimColor = Color.FromHex("#d14646");
    scale.MinorTicksPerInterval = 0;
    circularGauge.Scales = scale;
    this.Content= circulargauge;

{% endhighlight %}

## Adding Ranges

You can add ranges to `SfCircularGauge` by creating ranges collection using **Ranges**.

{% highlight c# %}

    Range range=new Range();
    range.StartValue=0;
    range.EndValue = 80;
    range.Color = Color.FromHex("#FF777777");
    range.Thickness = 10;
    scale.Ranges.Add(range);
    circularGauge.Scales = scale; 
    this.Content= circulargauge;

{% endhighlight %}

## Adding a Needle Pointer

You can create a `NeedlePointer` and associate it with a scale to display the current value.

{% highlight c# %}

    NeedlePointer needlePointer = new NeedlePointer(); 
    needlePointer.Value = 60; 
    needlePointer.Color = Color.White; 
    needlePointer.KnobColor = Color.White;
    needlePointer.Thickness = 5;
    needlePointer.KnobRadius = 20;
    needlePointer.LengthFactor= 0.8;
    scale.Pointers.Add(needlePointer); 
    circularGauge.Scales = scale; 

{% endhighlight %}

## Adding a Range Pointer

A `RangePointer` provides an alternative way of indicating the current value.

{% highlight c# %}
    
    ... 
    RangePointer rangePointer = new RangePointer();
    rangePointer.Value = 60; 
    rangePointer.Color = Color.FromHex("#2bbfb8");
    rangePointer.Thickness = 20; 
    scale.Pointers.Add(rangePointer);
    ...
    
 {% endhighlight %}
 
![](getting-started_images/default.png)