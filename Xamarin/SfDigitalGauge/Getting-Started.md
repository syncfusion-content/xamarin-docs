---
layout: post
title: Getting Started with Syncfusion DigitalGauge control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion digitalGauge control for Xamarin.Forms platform
platform: Xamarin
control: DigitalGauge
documentation: ug
---
# Getting Started

This section explains the steps required to configure the [`SfDigitalGauge`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfDigitalGauge.html) and add basic elements to it using various APIs.

## Adding digital gauge reference

Syncfusion components for Xamarin.Forms are available in nuget.org. To add [`SfDigitalGauge`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfDigitalGauge.html) to your project, open the NuGet package manager in Visual Studio, search for Syncfusion.Xamarin.SfGauge, and then install it.

To learn more about obtaining our components, refer to these links: Mac and Windows. Also, if you prefer to manually refer the assemblies instead of NuGet, refer to this link to learn about the dependent assemblies for digital gauge.

I> After adding the reference, an additional step is required for iOS and UWP projects. You should create an instance of the SfGaugeRenderer in iOS and UWP projects as shown in this KB article.

I> For UWP alone, one more additional step is required if the project is built-in release mode with .NET Native tool chain enabled. You can refer to this KB article for more details.

## Adding namespace for the assemblies

{% tabs %}

{% highlight xml %}

xmlns:gauge="clr-namespace:Syncfusion.SfGauge.XForms;assembly=Syncfusion.SfGauge.XForms"

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfGauge.XForms;

{% endhighlight %}

{% endtabs %}


## Initialize gauge

You can initialize the [`SfDigitalGauge`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfDigitalGauge.html) control with a required optimal name using the included namespace.

{% tabs %}

{% highlight xml %}

     <gauge:SfDigitalGauge/> 

{% endhighlight %}

{% highlight c# %}

SfDigitalGauge sfDigitalGauge = new SfDigitalGauge();

this.Content = sfDigitalGauge;

{% endhighlight %}

{% endtabs %}

## Setting value for digital gauge

The [`SfDigitalGauge`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfDigitalGauge.html) control provides options to display special characters or values using the [`Value`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfDigitalGauge~Value.html) property.

{% tabs %}

{% highlight xml %}

      <gauge:SfDigitalGauge Value="1 2 3 4"/>

{% endhighlight %}

{% highlight c# %}

SfDigitalGauge sfDigitalGauge = new SfDigitalGauge();

sfDigitalGauge.Value = "11:59:50 PM";

{% endhighlight %}

{% endtabs %}

## Setting character type for digital gauge

By using the [`CharacterType`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfDigitalGauge~CharacterType.html) property, you can set the segments for digital gauge. The digital characters can be drawn in the following four different segments:

•	EightCrossEightDotMatrix

•	SegmentFourteen

•	SegmentSeven

•	SegmentSixteen

{% tabs %}

{% highlight xml %}

     <gauge:SfDigitalGauge CharacterType="EightCrossEightDotMatrix"/>

{% endhighlight %}

{% highlight c# %}

SfDigitalGauge digital = new SfDigitalGauge();

digital.CharacterType = CharacterType.EightCrossEightDotMatrix;

{% endhighlight %}

{% endtabs %}

## Configuring properties

The [`CharacterHeight`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfDigitalGauge~CharacterHeight.html), [`CharacterWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfDigitalGauge~CharacterWidth.html), and [`CharacterStroke`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfDigitalGauge~CharacterStrokeColor.html)properties are used to display characters, which can be customized as shown in the following code snippets:

{% tabs %}

{% highlight xml %}

       <gauge:SfDigitalGauge  CharacterHeight="60" CharacterWidth="25" 
                                                    
                          CharacterStrokeColor="#146CED"/>


{% endhighlight %}

{% highlight c# %}

            SfDigitalGauge digital = new SfDigitalGauge();

            digital.CharacterHeight = 60;

            digital.CharacterWidth = 25;

            digital.CharacterStrokeColor = Color.FromRgb(20, 108, 237);

{% endhighlight %}

{% endtabs %}

The following code example is the complete code of the previous configurations.

{% tabs %}

{% highlight xml %}

     <?xml version="1.0" encoding="utf-8" ?>
       <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GaugeGettingStarted"
             x:Class="GaugeGettingStarted.MainPage"
             xmlns:gauge="clr-namespace:Syncfusion.SfGauge.XForms;assembly=Syncfusion.SfGauge.XForms">

         <gauge:SfDigitalGauge Value="11:59:50 PM" SegmentStrokeWidth="5" BackgroundColor="White"
                               HeightRequest="100"  WidthRequest="375"
                               DisabledSegmentAlpha="25" DisabledSegmentColor="Gray"
                               CharacterHeight="90" CharacterWidth="25" 
                               HorizontalOptions="Center" VerticalOptions="Center"
                               CharacterType="EightCrossEightDotMatrix" 
                               CharacterStrokeColor="#146CED"/>
      </ContentPage>

{% endhighlight %}

{% highlight c# %}

using Xamarin.Forms;

using Syncfusion.SfGauge.XForms;

namespace GaugeGettingStarted

{

    public partial class MainPage : ContentPage

    {

        public MainPage()
        {
            InitializeComponent();

            //Initialize digital gauge

            SfDigitalGauge digital = new SfDigitalGauge();
            
            digital.BackgroundColor = Color.White;

            digital.HeightRequest = 100;

            digital.WidthRequest = 375;

            digital.Value = "11:59:50 PM";

            digital.CharacterHeight = 90;

            digital.CharacterWidth = 25;

            digital.HorizontalOptions = LayoutOptions.Center;

            digital.VerticalOptions = LayoutOptions.Center;

            digital.SegmentStrokeWidth = 5;

            digital.CharacterType = CharacterType.EightCrossEightDotMatrix;

            digital.DisabledSegmentAlpha = 25;

            digital.CharacterStrokeColor = Color.FromRgb(20, 108, 237);

            digital.DisabledSegmentColor = Color.Gray;

            this.Content = digital;

        }
    }
}

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the result of the previous codes.

![](Getting_Started_images/Getting_Started_img1.jpeg)


You can find the complete getting started sample from this [`link`]().

