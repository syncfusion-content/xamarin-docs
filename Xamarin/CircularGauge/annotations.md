---

layout: post
title: Annotations in Syncfusion SfCircularGauge control for Xamarin.Forms
description: Learn how to set annotations in Syncfusion SfCircularGauge control
platform: xamarin
control: SfCircularGauge
documentation: ug

---

# Annotations

`SfCircularGauge` supports `Annotations`, and it allows you to mark the specific area of interest in circulargauge. Custom shapes can be drawn, and text and images also can be added by using `Annotations`.

## Sub Gauge

When the annotation allows to place custom elements, a gauge can be initialized to the element, and it can be used to place that in another gauge. The Following properties are used to customize the `Annotations`:-

* `Angle` - Used to place the `View` at the given `Angle`. 
* `Offset` - Used to move the `View` from center to edge of the circulargauge. The value should be range from 0 to 1.

The following code is used to create the `Annotations`.

{% tabs %}

{% highlight xaml %}
  
    
    <gauge:SfCircularGauge.Annotations>
        <gauge:GaugeAnnotation Angle="180" Offset="0.5">
            <gauge:GaugeAnnotation.View>
                <gauge:SfCircularGauge x:Name="gauge" />
            </gauge:GaugeAnnotation.View>
        </gauge:GaugeAnnotation>
	</gauge:SfCircularGauge.Annotations>
	
{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circular = new SfCircularGauge();
    SfCircularGauge gauge = new SfCircularGauge();
    CircularGaugeAnnotationCollection annotations = new CircularGaugeAnnotationCollection();
    GaugeAnnotation gaugeAnnotation = new GaugeAnnotation();
    gaugeAnnotation.Angle = 180;
    gaugeAnnotation.Offset = 0.5;
    gaugeAnnotation.View = gauge;
    annotations.Add(gaugeAnnotation);
    circularGauge.Annotations = annotations;
    this.Content = circular;
    
{% endhighlight %}

{% endtabs %}

![](annotations_images/annotations.png)