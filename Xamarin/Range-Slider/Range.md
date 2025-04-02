---
layout: post
title: Range in Xamarin Range Slider control | Syncfusion
description: Learn here all about Range support in Syncfusion Xamarin Range Slider (SfRangeSlider) control and more.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Range in Xamarin Range Slider (SfRangeSlider)

The [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html) control supports to select range of value by using two Thumbs.

## Set Show Range

The [`ShowRange`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ShowRange) property should be set to true for displaying two thumbs in track with range of values.

N> When this property is set to false, single thumb is displayed without any range 

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ShowRange="true"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ShowRange= true;

{% endhighlight %}

{% endtabs %}


## Set Range values

This section explains about setting Range start and end value.

### RangeStart

Gets and sets the start value of the range.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider"  RangeStart="4" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.RangeStart=0;

{% endhighlight %}

{% endtabs %}

### RangeEnd

Gets and sets the end value of the range.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" RangeEnd="20" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.RangeEnd=10;

{% endhighlight  %}

{% endtabs %}

## ValueChangeMode

The [`ValueChangeMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueChangeMode.html) property changes the value based on the touch of the [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html) control. It consists of the following two types

* [`Default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueChangeMode.html#Syncfusion_SfRangeSlider_XForms_ValueChangeMode_Default)
* [`OnThumbPress`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueChangeMode.html#Syncfusion_SfRangeSlider_XForms_ValueChangeMode_OnThumb)

N> The default value of the [`ValueChangeMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueChangeMode.html) property is [`Default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueChangeMode.html#Syncfusion_SfRangeSlider_XForms_ValueChangeMode_Default).


### Default

The value is updated when you touch inside the control.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider"  ValueChangeMode="Default" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ValueChangeMode = ValueChangeMode.Default;

{% endhighlight %}

{% endtabs %}

### OnThumb

The value is updated when you touch or move the thumb/knob.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider"  ValueChangeMode="OnThumb" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ValueChangeMode = ValueChangeMode.OnThumb;

{% endhighlight %}

{% endtabs %}


## Value

Gets or sets the range value, which ranges between [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_Maximum). The default value of RangeSlider is 0.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Minimum="0" Maximum="100" Value="30"/>
	
{% endhighlight %}

{% highlight c# %}

            rangeslider.Value = 30;

{% endhighlight  %}

{% endtabs %}

![Range value in SfRangeSlider in Xamarin.Forms](images/Value.jpg)


## Allow drag range.

Enable or disable the drag options to change a value of the ranges by using the [`AllowDragRange`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_AllowDragRange) property.

{% tabs %}

{% highlight xaml %}

<range:SfRangeSlider x:Name="rangeslider" AllowDragRange = "True" ShowRange = "True"  Minimum="0" Maximum="100" Value="30"/>
	
{% endhighlight %}

{% highlight c# %}

rangeslider.AllowDragRange = true;

{% endhighlight  %}

{% endtabs %}

![Allow Drag Range in SfRangeSlider in Xamarin.Forms](images/AllowDragRangeImage.gif)
