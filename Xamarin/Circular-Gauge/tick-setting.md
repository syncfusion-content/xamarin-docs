---

layout: post
title: Tick Setting in Syncfusion SfCircularGauge control for Xamarin.Forms
description:  Learn how to set ticks, position the ticks and customize the ticks in Syncfusion CircularGauge control for Xamarin.Forms
platform: xamarin
control: SfCircularGauge
documentation: ug

---

# Tick Settings in SfCircularGauge

The `TickSettings` property helps you to identify the gauge’s data value by marking the gauge scale in regular increments.

## Show ticks for scale

The [`ShowTicks`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.Scale.html#Syncfusion_SfGauge_XForms_Scale_ShowTicks) property allows you to enable or disable the ticks of circular gauge.

{% tabs %}

{% highlight xaml %}

    <gauge:SfCircularGauge>
  
    <gauge:SfCircularGauge.Scales>
         <gauge:Scale  ShowTicks=”False”/>
    </gauge:SfCircularGauge.Scales>

	</gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
	scale.ShowTicks = false;
    scales.Add(scale);
    circularGauge.Scales = scales;  

{% endhighlight %}

{% endtabs %}

![Show tick support in Xamarin.Forms Circular Gauge](tick-setting_images/show-ticks.png)

## Ticks customization 

The [`Interval`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.Scale.html#Syncfusion_SfGauge_XForms_Scale_Interval) property is used to calculate the tick counts for a scale. Similar to ticks, minor ticks are calculated by using the [`MinorTicksPerInterval`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.Scale.html#Syncfusion_SfGauge_XForms_Scale_MinorTicksPerInterval) property.

Color and thickness of the tick are set by using the [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.TickSettings.html#Syncfusion_SfGauge_XForms_TickSettings_Color) and [`Thickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.TickSettings.html#Syncfusion_SfGauge_XForms_TickSettings_Thickness) UI properties. You can also customize the length of the ticks by using the  [`Length`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.TickSettings.html#Syncfusion_SfGauge_XForms_TickSettings_Length) property. First, you should set the `Offset` property for ticks, then increase the length of the ticks.

## Customize major ticks for scale

{% tabs %}

{% highlight xaml %}

      <gauge:SfCircularGauge>

        <gauge:SfCircularGauge.Scales>

            <gauge:Scale>

                <gauge:Scale.MajorTickSettings>
                    <gauge:TickSettings Color ="Brown" Thickness="4" Length="15" Offset="0.97"/>
                </gauge:Scale.MajorTickSettings>

            </gauge:Scale>

        </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    TickSettings majorTicks = new TickSettings();
    majorTicks.Length = 15;
    majorTicks.Color = Color.Brown;
    majorTicks.Thickness = 4;
    majorTicks.Offset = 0.97;
    scale.MajorTickSettings = majorTicks;
    scales.Add(scale);
    circularGauge.Scales = scales;  
  
{% endhighlight %}

{% endtabs %}

![Tick customization in Xamarin.Forms Circular Gauge](tick-setting_images/majortick-customise.png)

## Customize minor ticks for scale

{% tabs %}

{% highlight xaml %}

      <gauge:SfCircularGauge>

        <gauge:SfCircularGauge.Scales>

            <gauge:Scale>

                <gauge:Scale.MinorTickSettings>
                    <gauge:TickSettings Color ="SkyBlue" Thickness="4" Length="4" Offset = "0.97" />
                </gauge:Scale.MinorTickSettings>

            </gauge:Scale>

        </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    TickSettings minorTicks = new TickSettings();
    minorTicks.Length = 4;
    minorTicks.Color = Color.SkyBlue;
    minorTicks.Thickness = 4;
    minorTicks.Offset = 0.97;
    scale.MinorTickSettings = minorTicks;   
    scales.Add(scale);
    circularGauge.Scales = scales;  
  
{% endhighlight %}

{% endtabs %}

![Minor tick customization in Xamarin.Forms Circular Gauge](tick-setting_images/minortick-customise.png)

## Setting position for ticks

The major and minor ticks can be positioned far away from the rim by using the following two ways:

1.[`Offset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.TickSettings.html#Syncfusion_SfGauge_XForms_TickSettings_Offset) property. 
2.[`StartOffset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.TickSettings.html#Syncfusion_SfGauge_XForms_TickSettings_StartOffset) and [`EndOffset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.TickSettings.html#Syncfusion_SfGauge_XForms_TickSettings_EndOffset) properties.

### Setting offset for scale

{% tabs %}

{% highlight xaml %}

        <gauge:SfCircularGauge>

        <gauge:SfCircularGauge.Scales>

            <gauge:Scale>

                <gauge:Scale.MajorTickSettings>
                    <gauge:TickSettings Offset = "0.5"/>
                </gauge:Scale.MajorTickSettings>

                <gauge:Scale.MinorTickSettings>
                    <gauge:TickSettings Offset = "0.5"/>
                </gauge:Scale.MinorTickSettings>

            </gauge:Scale>

        </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
	TickSettings majorTicks = new TickSettings();
    majorTicks.Offset = 0.5;
    scale.MajorTickSettings = majorTicks;
    TickSettings minorTicks = new TickSettings();
    minorTicks.Offset = 0.5;
    scale.MinorTickSettings = minorTicks; 
    scales.Add(scale);
    circularGauge.Scales = scales;  
  
{% endhighlight %}

{% endtabs %}

![Positioning tick in Xamarin.Forms Circular Gauge](tick-setting_images/offset.png)

### Setting scale start and end offset for scale

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>


        <gauge:SfCircularGauge.Scales>

            <gauge:Scale>

                <gauge:Scale.MajorTickSettings>
                    <gauge:TickSettings StartOffset = "0.3" EndOffset ="0.4"/>
                </gauge:Scale.MajorTickSettings>

                <gauge:Scale.MinorTickSettings>
                    <gauge:TickSettings StartOffset = "0.3" EndOffset ="0.35"/>
                </gauge:Scale.MinorTickSettings>

            </gauge:Scale>

        </gauge:SfCircularGauge.Scales>

    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
	TickSettings majorTicks = new TickSettings();
    majorTicks.StartOffset = 0.3;
    majorTicks.EndOffset = 0.4;
    scale.MajorTickSettings = majorTicks;
    TickSettings minorTicks = new TickSettings();
    minorTicks.StartOffset = 0.3;
    minorTicks.EndOffset = 0.35;
    scale.MinorTickSettings = minorTicks; 
   
    scales.Add(scale);
    circularGauge.Scales = scales;  
  
{% endhighlight %}

{% endtabs %}

![Tick offset support in Xamarin.Forms Circular Gauge](tick-setting_images/start-end-offset.png)

## See Also

[How to show labels and ticks outside the rim in Xamarin.Forms Radial Gauge](https://www.syncfusion.com/kb/11283/how-to-show-labels-and-ticks-outside-the-rim-in-xamarin-forms-radial-gauge)

[How to set ticks and customize its position in circular gauge](https://www.syncfusion.com/kb/8297/how-to-set-ticks-and-customize-its-position-in-circular-gauge)