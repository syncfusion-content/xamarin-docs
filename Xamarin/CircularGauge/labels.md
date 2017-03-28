---

layout: post
title: Labels in Syncfusion SfCircularGauge control for Xamarin.Forms
description:  Learn how to set labels in Syncfusion SfCircularGauge control
platform: xamarin
control: SfCircularGauge
documentation: ug

---

# LABELS

Scale labels associate a numeric value with major scale tick marks.

## Label Customization

The label color can be changed using the `LabelColor` property. The labels can be positioned far away from the ticks by using the `LabelOffset` property.The size of the Labels can be changed by using the `LabelFontSize` property.

{% tabs %}

{% highlight xaml %}

    <gauge:SfCircularGauge.Scales>
        <gauge:Scale StartAngle="135" StartValue="0" EndValue="100" Interval="10" SweepAngle="270"  
                   LabelOffset="0.1" LabelColor="Gray" LabelFontSize="10"/>      
    </gauge:SfCircularGauge.Scales>                

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale=new Scale();
    scale.LabelColor = Color.Gray;
    scale.LabelOffset = 0.1;
    scale.LabelFontSize=10;
    scales.Add(scale);
    circulargauge.Scales = scales;  
    this.content=circulargauge;
    
{% endhighlight %}

{% endtabs %}
## Number of Decimal Digits

The `NumberOfDecimalDigits` property is used to set the number of decimal digits to be displayed in the scale labels.

{% tabs %}

{% highlight xaml %}

    <gauge:SfCircularGauge.Scales>
        <gauge:Scale StartAngle="135" StartValue="0" EndValue="100" Interval="10" SweepAngle="270"  
                   NumberOfDecimalDigits="1"/> 
    </gauge:SfCircularGauge.Scales>                

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale=new Scale();
    Scale.NumberOfDecimalDigits=1;
    scales.Add(scale);
    circulargauge.Scales = scales;
    this.content=circulargauge;
    
{% endhighlight %}

{% endtabs %}
![](labels_images/label-customization/label-customization.png)

## Label Postfix and Prefix

You can set the postfix/Prefix values to the scale labels using `LabelPostfix` and `LabelPrefix` Properties respectively.

### LabelPostfix

This property allows you to set the postfix values to the scale labels.

{% tabs %}

{% highlight xaml %}

    <gauge:SfCircularGauge.Scales>
        <gauge:Scale StartAngle="135" StartValue="0" EndValue="100" Interval="10" SweepAngle="270"  
                   LabelPostfix="%"/> 
    </gauge:SfCircularGauge.Scales>                

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale=new Scale();
    Scale.LabelPostfix="%";
    scales.Add(scale);
    circulargauge.Scales = scales;
    this.content=circulargauge;
    
{% endhighlight %}

{% endtabs %}

![](labels_images/label-postfix/label-postfix.png)

### LabelPrefix
This property allows you to set the prefix values to the scale labels.

{% tabs %}

{% highlight xaml %}

    <gauge:SfCircularGauge.Scales>
        <gauge:Scale StartAngle="135" StartValue="0" EndValue="100" Interval="10" SweepAngle="270"  
                   LabelPrefix="$"/> 
    </gauge:SfCircularGauge.Scales>                

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge();
    ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
    Scale scale=new Scale();
    Scale.LabelPrefix="$";
    scales.Add(scale);
    circulargauge.Scales = scales;
    this.content=circulargauge;
    
{% endhighlight %}
{% endtabs %}

![](labels_images/label-prefix/label-prefix.png)

### ShowLabels

ShowLabels property is a Boolean property which is used to enable or disable feature of labels in CircularGauge

{% tabs %}

{% highlight xaml %}

        <gauge:SfCircularGauge x:Name="circularGauge">
          <gauge:SfCircularGauge.Scales>
	  	    <gauge:Scale x:Name="scale" ShowLabels="False">
                    </gauge:Scale>
	      </gauge:SfCircularGauge.Scales>			
	    </gauge:SfCircularGauge>	 

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge circulargauge = new SfCircularGauge();       
            ObservableCollection<Scale> scales = new ObservableCollection<Scale>();
            Scale scale = new Scale();                
            scale.ShowLabels = false;
            scales.Add(scale);
            circulargauge.Scales.Add(scale);
            this.Content = circulargauge;
   
    
{% endhighlight %}
{% endtabs %}


