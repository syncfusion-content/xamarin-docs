---

layout: post
title: Tick Setting in Syncfusion SfCircularGauge control for Xamarin.Forms
description:  Learn how to set ticks in Syncfusion SfCircularGauge control
platform: xamarin
control: SfCircularGauge
documentation: ug

---

# TICK SETTING

Ticks help you identify the gauge’s data value by marking the gauge scale in regular increments.

## Tick Customization  

The `Interval` property is used to calculate the tick count for a scale. Like ticks, minor ticks are calculated using the `MinorTicksPerInterval` property.

A tick’s length, color, and thickness are set by the `Length`, `Color` and `Thickness` UI properties.

The tick’s position from the rim is set using the `Offset` property.

{% tabs %}

{% highlight xaml %}
  
    <gauge:SfCircularGauge.Scales>
      <gauge:Scale StartAngle="135" StartValue="0" EndValue="100" Interval="10" SweepAngle="270"
                   RimThickness="20" RimColor="Gray" MinorTicksPerInterval="1">
        
          <gauge:Scale.MajorTickSettings>
              <gauge:TickSettings Length="12" Color ="#2bbfb8" Thickness="3"/>
            </gauge:Scale.MajorTickSettings>
              
          <gauge:Scale.MinorTickSettings>
              <gauge:TickSettings  Length="6" Color ="#2bbfb8"  Offset="0.5" Thickness="3"/>
           </gauge:Scale.MinorTickSettings>               
    
      </gauge:Scale>
    </gauge:SfCircularGauge.Scales>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circular = new SfCircularGauge();
    scale.MinorTicksPerInterval = 1;
    TickSettings minor = new TickSettings();
    minor.Length = 6;
    minor.Color = Color.FromHex("#2bbfb8");
    minor.Thickness = 3;
	minor.Offset = 0.5;
    scale.MinorTickSettings = minor;
    TickSettings major = new TickSettings();
    major.Length = 12;
    major.Color = Color.FromHex("#2bbfb8");
    major.Thickness = 3;
    scale.MajorTickSettings = major;
    circular.Scales = scale;
    this.Content= circular;
    
{% endhighlight %}

{% endtabs %}

![](tick-setting_images/offset.png)