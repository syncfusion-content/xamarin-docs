---

layout: post
title: Tick Setting in Syncfusion SfCircularGauge control for Xamarin.Forms
description:  Learn how to set ticks in Syncfusion SfCircularGauge control
platform: Xamarin.Forms
control: SfCircularGauge
documentation: ug

---

# TICK SETTING

Ticks help you identify the gauge’s data value by marking the gauge scale in regular increments.

## Tick Customization  

The `Interval` property is used to calculate the tick count for a scale. Like ticks, minor ticks are calculated using the `MinorTicksPerInterval` property.

A tick’s length, color, and thickness are set by the `Length`, `Color` and `Thickness` UI properties.

The tick’s position from the rim is set using the `Offset` property.

{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge();
    TickSettings minor = new TickSettings();
    minor.Length = 6;
    minor.Color = Color.FromHex("#444444");
    minor.Thickness = 3;
	minor.Offset = 0.5;
    scale.MinorTickSettings = minor;
    TickSettings major = new TickSettings();
    major.Length = 12;
    major.Color = Color.FromHex("#444444");
    major.Thickness = 3;
	major.Offset = 0.5;
    major.Offset = Device.OnPlatform(0.05, 0.1,0.3);
    scale.MajorTickSettings = major;
    circulargauge.Scales = scale;
    this.Content= circulargauge;
    
{% endhighlight %}

![](tick-setting_images/offset.png)