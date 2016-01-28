---

layout: post
title: Scales in Syncfusion SfCircularGauge control for Xamarin.Forms
description:  Learn how to set scales in Syncfusion SfCircularGauge control
platform: Xamarin.Forms
control: SfCircularGauge
documentation: ug

---

# SCALES

The Scales contains a Collection of CircularScale which integrates labels, tick marks, and a rim to customize the basic look and feel of the **SfCircularGauge**.

## Scale

CircularScale contains three sub elements such as Rim, Ticks, and Labels, Range, Pointers. It defines the Radius, start angle, sweep direction and sweep angle, overall minimum and maximum values, and frequency of labels and tick marks. It can have multiple ranges. 

A range is a visual element which begins and ends at specified values within a scale. It can have one or more pointers to point out the values in the scale.

{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge();
    scale = new Scale();
    scale.StartValue = 0;
    scale.EndValue = 100;
    scale.Interval = 10;
    scale.StartAngle = 135;
    scale.SweepAngle = 270;
    scale.RimThickness = 20;
    scale.RimColor = Color.FromHex("#d14646");
    scale.LabelColor = Color.Gray;
    scale.LabelOffset = 0.1;
    scale.MinorTicksPerInterval = 1;
    circulargauge.Scales = scale;
    this.content=circulargauge;
    
{% endhighlight %}

![](scales_images/scale.png)

## Multiple Scale

It helps to be able to add multiple scales to the same circular gauge, and also it helps to customize all the scales in a Scales collection.