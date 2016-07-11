---
layout : post
title : Transformation in Syncfusion Carousel control in Xamarin.Forms
description : Learn how to set the Rotation Angle and Offset in Carousel for Xamarin.Forms
platform : Xamarin
control : Carousel
documentation : ug
---

# Transformation

## Rotation Angle

The `RotationAngle` property in the SfCarousel control is used to rotate all the unselected items in a specified angle. 

N> If the angle value is positive, then the rotation is in the clockwise direction. If the angle value is negative, the rotation is in the counterclockwise direction. 

{% tabs %}

{% highlight C# %}

	carousel.RotationAngle=40;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" RotationAngle="45" />
	
{% endhighlight %}

{% endtabs %}

![](images/rotationangle.png)

## Offset

### Offset between items

The `Offset` property is used to specify the accurate distance between unselected items in SfCarousel panel.  

N> The default value is 20.

{% tabs %}

{% highlight C# %}

	carousel.Offset=30;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" Offset="30" />
	
{% endhighlight %}

{% endtabs %}

![](images/offset.png)

### Offset around selected item

Distance between the selected item and other items can be customized by using `SelectedItemOffset` property of the SfCarousel control.

{% tabs %}

{% highlight C# %}

	carousel.SelectedItemOffset=5;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" SelectedItemOffset="5" />
	
{% endhighlight %}

{% endtabs %}

### Scale Offset

The `ScaleOffset` property in the SfCarousel control is used to scale all the items to the specified scale value.

{% tabs %}

{% highlight C# %}
	
	carousel.ScaleOffset=0.7f;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" ScaleOffset="0.7f" />
	
{% endhighlight %}

{% endtabs %}

![](images/scaleoffset.png)

