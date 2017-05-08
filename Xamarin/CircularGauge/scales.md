---

layout: post
title: Scales in Syncfusion SfCircularGauge control for Xamarin.Forms
description:  Learn how to set scales in Syncfusion SfCircularGauge control
platform: xamarin
control: SfCircularGauge
documentation: ug

---

# SCALES

The Scales contains a Collection of CircularScale which integrates labels, tick marks, and a rim to customize the basic look and feel of the `SfCircularGauge`.

## Scale

CircularScale contains sub elements such as Rim, Ticks, and Labels, Range, Pointers. It defines the Radius, start angle, sweep direction and sweep angle, overall minimum and maximum values, and frequency of labels and tick marks. It can have multiple ranges. 

A range is a visual element which begins and ends at specified values within a `scale`. It can have one or more pointers to point out the values in the scale.

{% tabs %}

{% highlight xaml %}

    <gauge:SfCircularGauge.Scales>
         <gauge:Scale NumberOfDecimalDigits="4" StartAngle="135" StartValue="0" EndValue="100" Interval="10" SweepAngle="270"
                   RimThickness="20" RimColor="Gray" MinorTicksPerInterval="0">
         </gauge:Scale>
    </gauge:SfCircularGauge.Scales>

{% endhighlight %}

{% highlight c# %}

    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    scale.StartValue = 0; 
    scale.EndValue = 100;
    scale.Interval = 10;
    scale.StartAngle = 135;
    scale.SweepAngle = 270;
    scale.RimThickness =  20;
    scale.RimColor = Color.Gray;
    scale.MinorTicksPerInterval = 0;
    scales.Add(scale);
    circulargauge.Scales = scales;  
    this.Content= circulargauge;

{% endhighlight %}

{% endtabs %}

![](scales_images/scale.png)

## Multiple Scale

It helps to be able to add multiple scales to the same circular gauge, and also it helps to customize all the scales in a Scales collection.

## ShowTicks

ShowTicks property is Boolean property that enables or disables the Tick feature of the SfCircularGauge.

{% tabs %}

{% highlight xaml %}

    <gauge:SfCircularGauge.Scales>
         <gauge:Scale ShowTicks="False"/>
    </gauge:SfCircularGauge.Scales>

{% endhighlight %}

{% highlight c# %}

    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale = new Scale();
    scale.ShowTicks = False;
    scales.Add(scale);
    circulargauge.Scales = scales;  
    this.Content= circulargauge;
{% endhighlight %}
    
{% endtabs %}
