---
layout: post
title: Rim in Syncfusion SfCircularGauge control for Xamarin.Forms
description: Learn how to access rim in Syncfusion SfCircularGauge control for Xamarin.Forms Platform
platform: xamarin
control: SfCircularGauge
documentation: ug
---

# RIM

`Scale` determines the structure of the circular gauge using the circular rim. By setting the `StartAngle` and `SweepAngle` properties, you can shape the circular gauge into a full circular gauge, half circular gauge, or quarter circular gauge.

The `StartValue` and `EndValue` properties will determine the overall range of the circular rim. The rim’s color and thickness can be set using the `RimColor` and `RimThickness` properties.

{% tabs %}

{% highlight xaml %}

    <gauge:SfCircularGauge.Scales>
        <gauge:Scale StartAngle="135" StartValue="0" EndValue="100" Interval="10" SweepAngle="270" LabelOffset="0.1" 
                   LabelColor="Gray" LabelFontSize="10" LabelOffset="0.1"
                   RimThickness="10" RimColor="Gray" MinorTicksPerInterval="0">
        </gauge:Scale>
    </gauge:SfCircularGauge.Scales>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale=new Scale();
    scale.StartValue = 0;
    scale.EndValue = 100;
    scale.Interval = 10;
    scale.StartAngle = 135;
    scale.SweepAngle = 270;
    scale.RimThickness = 10;
    scale.RimColor = Color.Gray;
    scale.LabelColor = Color.Gray;
    scale.LabelOffset = 0.1;
    scale.MinorTicksPerInterval = 0;
    scales.Add(scale);
    circulargauge.Scales = scales;
    this.content=circulargauge;

{% endhighlight %}

{% endtabs %}

![](rim_images/rim.png)

## Show Rim

Show Rim property is a Boolean property which is used to enable or disable feature of Rim in CircularGauge

{% tabs %}

{% highlight xaml %}

        <gauge:SfCircularGauge x:Name="circularGauge">
          <gauge:SfCircularGauge.Scales>
	  	    <gauge:Scale x:Name="scale" ShowRim = "False">
                    </gauge:Scale>
	      </gauge:SfCircularGauge.Scales>			
	    </gauge:SfCircularGauge>	 

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge circulargauge = new SfCircularGauge();       
            ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
            Scale scale = new Scale();                
            scale.ShowRim = false;
            scales.Add(scale);
            circulargauge.Scales.Add(scale);
            this.Content = circulargauge;
   
    
{% endhighlight %}
{% endtabs %}

