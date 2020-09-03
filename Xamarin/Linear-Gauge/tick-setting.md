---
layout: post
title: Tick Settings in Syncfusion LinearGauge control for Xamarin.Forms
description: This section describes how to define settings of linear ticks in SfLinearGauge control for Xamarin.Forms
platform: Xamarin
control: LinearGauge
documentation: ug
---

# Tick Setting in SfLinearGauge

The [`TickSetting`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.TickSettings.html) property is used to identify the gauge’s data value by marking the gauge scale in regular increments.

## Ticks visibility

Ticks visibility can be customized using the [`ShowTicks`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearScale.html#Syncfusion_SfGauge_XForms_LinearScale_ShowTicks) property of linear scale.

{% tabs %}

{% highlight xaml %}

	 <gauge:SfLinearGauge>
            <gauge:SfLinearGauge.Scales>
                <gauge:LinearScale ScaleBarColor="#e0e0e0" LabelColor="#424242" LabelOffset ="-10" ShowTicks ="False">
                </gauge:LinearScale>
            </gauge:SfLinearGauge.Scales>
        </gauge:SfLinearGauge>
	
{% endhighlight %}

{% highlight C# %}

		    SfLinearGauge linearGauge = new SfLinearGauge();
            LinearScale linearScale = new LinearScale();
            linearScale.ScaleBarColor = Color.FromHex("#e0e0e0");
            linearScale.LabelColor = Color.FromHex("#424242");
            linearScale.LabelOffset = -10;
            linearScale.ShowTicks = false;
            linearGauge.Scales.Add(linearScale);
			
{% endhighlight %}

{% endtabs %}

![Linear Gauge Tick Settings](tick-setting_images/tick-setting1.png)

## Tick customization

You can customize the color and thickness of ticks by using the [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearTickSettings.html#Syncfusion_SfGauge_XForms_LinearTickSettings_Color) and [`Thickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearTickSettings.html#Syncfusion_SfGauge_XForms_LinearTickSettings_Thickness) properties. The ticks length also can be customized using the [`Length`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearTickSettings.html#Syncfusion_SfGauge_XForms_LinearTickSettings_Length) property as demonstrated below.

### Major tick customization

{% tabs %}

{% highlight xaml %}

	<gauge:SfLinearGauge>
            <gauge:SfLinearGauge.Scales>
                <gauge:LinearScale ScaleBarColor="#e0e0e0" LabelColor="#424242">
                    <gauge:LinearScale.MajorTickSettings>
                      <gauge:LinearTickSettings Thickness="1" Length ="25" Color = "DeepSkyBlue"/>
                    </gauge:LinearScale.MajorTickSettings>
                </gauge:LinearScale>
            </gauge:SfLinearGauge.Scales>
        </gauge:SfLinearGauge>
	
{% endhighlight %}

{% highlight C# %}

		    SfLinearGauge linearGauge = new SfLinearGauge();
            LinearScale linearScale = new LinearScale();
            linearScale.ScaleBarColor = Color.FromHex("#e0e0e0");
            linearScale.LabelColor = Color.FromHex("#424242");
            LinearTickSettings majorTickSettings = new LinearTickSettings();
            majorTickSettings.Thickness = 1;
            majorTickSettings.Length = 25;
            majorTickSettings.Color = Color.DeepSkyBlue;
            linearScale.MajorTickSettings = majorTickSettings;
            linearGauge.Scales.Add(linearScale);
			
{% endhighlight %}

{% endtabs %}

![Linear Gauge Tick Customization](tick-setting_images/tick-setting2.png)

### Minor tick customization

{% tabs %}

{% highlight xaml %}

	<gauge:SfLinearGauge>
            <gauge:SfLinearGauge.Scales>
                <gauge:LinearScale ScaleBarColor="#e0e0e0" LabelColor="#424242" MinorTicksPerInterval ="3">
                    <gauge:LinearScale.MinorTickSettings>
                      <gauge:LinearTickSettings Thickness="2" Length ="7" Color = "RosyBrown"/>
                    </gauge:LinearScale.MinorTickSettings>
                </gauge:LinearScale>
            </gauge:SfLinearGauge.Scales>
        </gauge:SfLinearGauge>
	
{% endhighlight %}

{% highlight C# %}

     SfLinearGauge linearGauge = new SfLinearGauge();
     LinearScale linearScale = new LinearScale();
     linearScale.ScaleBarColor = Color.FromHex("#e0e0e0");
     linearScale.LabelColor = Color.FromHex("#424242");
     linearScale.MajorTickSettings.Thickness = 1;
     linearScale.MinorTicksPerInterval = 3;
     LinearTickSettings minorTickSettings = new LinearTickSettings();
     minorTickSettings.Thickness = 2;
     minorTickSettings.Length = 7;
     minorTickSettings.Color = Color.RosyBrown;
     linearScale.MinorTickSettings = minorTickSettings;
     linearGauge.Scales.Add(linearScale);

			
{% endhighlight %}

{% endtabs %}

![Linear Gauge Majot Tick](tick-setting_images/tick-setting3.png)

## Setting minor ticks per interval

The [`Interval`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearScale.html#Syncfusion_SfGauge_XForms_LinearScale_Interval) property is used to calculate the tick counts for a scale. Similar to ticks, minor ticks are also calculated by using the [`MinorTicksPerInterval`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearScale.html#Syncfusion_SfGauge_XForms_LinearScale_MinorTicksPerInterval) property.

{% tabs %}

{% highlight xaml %}

	<gauge:SfLinearGauge>
            <gauge:SfLinearGauge.Scales>
                <gauge:LinearScale ScaleBarColor="#e0e0e0" LabelColor="#424242" MinorTicksPerInterval ="4">
                </gauge:LinearScale>
            </gauge:SfLinearGauge.Scales>
        </gauge:SfLinearGauge>
	
{% endhighlight %}

{% highlight C# %}

      SfLinearGauge linearGauge = new SfLinearGauge();
      LinearScale linearScale = new LinearScale();
      linearScale.ScaleBarColor = Color.FromHex("#e0e0e0");
      linearScale.LabelColor = Color.FromHex("#424242");
      linearScale.MinorTicksPerInterval = 4;
      linearGauge.Scales.Add(linearScale);
			
{% endhighlight %}

{% endtabs %}

![Linear Gauge Minor Tick](tick-setting_images/tick-setting4.png)

## Setting position for ticks

The major and minor ticks can be positioned far away from the scale by using the [`Offset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfGauge.XForms.LinearTickSettings.html#Syncfusion_SfGauge_XForms_LinearTickSettings_Offset) property.

{% tabs %}

{% highlight xaml %}

	<gauge:SfLinearGauge>
            <gauge:SfLinearGauge.Scales>
                <gauge:LinearScale ScaleBarColor="#e0e0e0" LabelColor="Black" ScaleBarSize ="40" LabelOffset = "-9">
				  <gauge:LinearScale.MajorTickSettings>
                      <gauge:LinearTickSettings Thickness="1" Color ="Black" Length ="40" Offset ="-40" />
                    </gauge:LinearScale.MajorTickSettings>
					<gauge:LinearScale.MinorTickSettings>
                      <gauge:LinearTickSettings Color ="Black" Length = "20" Offset ="-20" />
                    </gauge:LinearScale.MinorTickSettings>
                </gauge:LinearScale>
            </gauge:SfLinearGauge.Scales>
        </gauge:SfLinearGauge>
	
{% endhighlight %}

{% highlight C# %}

            SfLinearGauge linearGauge = new SfLinearGauge();
            LinearScale linearScale = new LinearScale();
            linearScale.ScaleBarSize = 40;
            linearScale.ScaleBarColor= Color.FromHex("#e0e0e0");
            linearScale.MajorTickSettings.Color = Color.Black;
            linearScale.MinorTickSettings.Color = Color.Black;
            linearScale.MajorTickSettings.Length = 40;
            linearScale.MinorTickSettings.Offset = -20;
            linearScale.MajorTickSettings.Offset = -40;
            linearScale.MajorTickSettings.Thickness = 1;
            linearScale.MinorTickSettings.Length = 20;
            linearScale.LabelOffset = -9;
            linearScale.MinorTicksPerInterval = 4;
            linearScale.LabelColor = Color.Black;
            linearGauge.Scales.Add(linearScale);
			
{% endhighlight %}

{% endtabs %}

![Linear Gauge Tick Position](tick-setting_images/tick-setting5.png)