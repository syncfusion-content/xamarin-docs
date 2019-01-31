---
layout: post
title: Orientation in LinearGauge
description: Learn how to set Orientation in LinearGauge
platform: Xamarin
control: LinearGauge
documentation: ug
---
# Change Orientation

[`SfLinearGauge`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfLinearGauge.html) supports horizontal and vertical orientations. By default, [`SfLinearGauge`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfLinearGauge.html) is rendered with horizontal orientation. You can the change the orientation by using the [`Orientation`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.SfLinearGauge~OrientationProperty.html) property. 

{% tabs %}

{% highlight xaml %}

	 <gauge:SfLinearGauge Orientation="OrientationVertical">
       <gauge:SfLinearGauge.Scales>
                <gauge:LinearScale Interval="10" ScaleBarLength="350" ScaleBarColor="#e0e0e0" LabelColor="#424242">
                 <gauge:LinearScale.MajorTickSettings>
                      <gauge:LinearTickSettings Thickness="1" />
                    </gauge:LinearScale.MajorTickSettings>
             </gauge:LinearScale>
        </gauge:SfLinearGauge.Scales>
       </gauge:SfLinearGauge>

	
{% endhighlight %}

{% highlight C# %}

            SfLinearGauge linearGauge = new SfLinearGauge();
            linearGauge.Orientation = Orientation.OrientationVertical;
            LinearScale linearScale = new LinearScale();
            linearScale.Interval = 10;
            linearScale.ScaleBarLength = 350;
            linearScale.MajorTickSettings.Thickness = 1;
            linearScale.ScaleBarColor = Color.FromHex("#e0e0e0");
            linearScale.LabelColor = Color.FromHex("#424242");
            linearGauge.Scales.Add(linearScale);


{% endhighlight %}

{% endtabs %}

![Linear Gauge Orientation](change-orientation_images/orientaion.png)
