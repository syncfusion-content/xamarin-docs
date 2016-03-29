---

layout: post
title: Rim in Syncfusion SfCircularGauge control for Xamarin.Forms
description: Learn how to access rim in Syncfusion SfCircularGauge control for Xamarin.Forms Platform
platform: Xamarin.Forms
control: SfCircularGauge
documentation: ug

---

# RIM

`Scale` determines the structure of the circular gauge using the circular rim. By setting the `StartAngle` and `SweepAngle` properties, you can shape the circular gauge into a full circular gauge, half circular gauge, or quarter circular gauge.

The `StartValue` and `EndValue` properties will determine the overall range of the circular rim. The rim’s color and thickness can be set using the `RimColor` and `RimThickness` properties.

{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge();
    Scale scale=new Scale();
    scale.StartValue = 0;
    scale.EndValue = 100;
    scale.Interval = 10;
    scale.StartAngle = 135;
    scale.SweepAngle = 270;
    scale.RimThickness = 10;
    scale.RimColor = Color.FromHex("#d14646");
    scale.LabelColor = Color.Gray;
    scale.LabelOffset = 0.1;
    scale.MinorTicksPerInterval = 0;
    circulargauge.Scales = scale;
    this.content=circulargauge;

{% endhighlight %}

![](rim_images/rim.png)