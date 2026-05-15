---
layout: post
title: Range in Xamarin Range Slider Control | Syncfusion
description: Learn about range selection support in the Syncfusion Xamarin Range Slider (SfRangeSlider) control and its functionalities.
platform: Xamarin
control: RangeSlider
documentation: ug
---

# Range in Xamarin Range Slider (SfRangeSlider)

The [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html) control supports selecting a range of values using two thumbs.

## Set Show Range

Configure the [`ShowRange`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ShowRange) property to true to display two thumbs on the track representing a range of values.

> **Note**: Setting this property to false displays a single thumb without the range.
{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" ShowRange="true"/>
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ShowRange= true;

{% endhighlight %}

{% endtabs %}

## Set Range Values

This section explains how to set the start and end values of the range.

### RangeStart

Get and set the starting value of the range.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider"  RangeStart="4" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.RangeStart=0;

{% endhighlight %}

{% endtabs %}

### RangeEnd

Get and set the ending value of the range.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" RangeEnd="20" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.RangeEnd=10;

{% endhighlight  %}

{% endtabs %}

## Value Change Mode

The [`ValueChangeMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueChangeMode.html) property alters the slider's value based on interaction with the [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html) control. There are two modes:

- [`Default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueChangeMode.html#Syncfusion_SfRangeSlider_XForms_ValueChangeMode_Default)
- [`OnThumbPress`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueChangeMode.html#Syncfusion_SfRangeSlider_XForms_ValueChangeMode_OnThumb)

> **Note**: The default setting is [`Default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueChangeMode.html#Syncfusion_SfRangeSlider_XForms_ValueChangeMode_Default).


### Default

The value updates when touching inside the control.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider"  ValueChangeMode="Default" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ValueChangeMode = ValueChangeMode.Default;

{% endhighlight %}

{% endtabs %}

### OnThumb

The value updates when touching or moving the thumb/knob.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider"  ValueChangeMode="OnThumb" />
	
{% endhighlight %}

{% highlight c# %}

	rangeSlider.ValueChangeMode = ValueChangeMode.OnThumb;

{% endhighlight %}

{% endtabs %}


## Value

Get or set the range value, which must be between the specified [`Minimum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_Minimum) and [`Maximum`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_Maximum) limits. The default value is 0.

{% tabs %}

{% highlight xaml %}

	<range:SfRangeSlider x:Name="rangeslider" Minimum="0" Maximum="100" Value="30"/>
	
{% endhighlight %}

{% highlight c# %}

            rangeslider.Value = 30;

{% endhighlight  %}

{% endtabs %}

![Range value in SfRangeSlider in Xamarin.Forms](images/Value.jpg)

## Allow Drag Range

Enable or disable drag options to adjust range values using the [`AllowDragRange`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_AllowDragRange) property.

{% tabs %}

{% highlight xaml %}

<range:SfRangeSlider x:Name="rangeslider" AllowDragRange = "True" ShowRange = "True"  Minimum="0" Maximum="100" Value="30"/>
	
{% endhighlight %}

{% highlight c# %}

rangeslider.AllowDragRange = true;

{% endhighlight  %}

{% endtabs %}

![Allow Drag Range in SfRangeSlider in Xamarin.Forms](images/AllowDragRangeImage.gif)
