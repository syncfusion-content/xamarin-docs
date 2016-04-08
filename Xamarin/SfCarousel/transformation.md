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

The `RotationAngle` property in the SfCarousel control is used to rotate all the items to a specified angle. 

N> If the angle value is positive, then the rotation is in the clockwise direction. If the angle value is negative, the rotation is in the counterclockwise direction. 

{% highlight C# %}

	carousel.RotationAngle=40;

{% endhighlight %}

![](images/rotationangle.png)

## Offset

### Offset between items

The `Offset` property used to specify the accurate distance between the items in Carousel panel.  

N> The default value is 20.

{% highlight C# %}

	carousel.Offset=30;

{% endhighlight %}

![](images/offset.png)

### Offset around selected item

Distance between the selected item and other items can be customized by using `SelectedItemOffset` property of the SfCarousel control.

{% highlight C# %}

	carousel.SelectedItemOffset=5;

{% endhighlight %}

### Scale Offset

The `ScaleOffset` property in the SfCarousel control is used to scale all the items to the specified scale value.

{% highlight C# %}
	
	carousel.ScaleOffset=0.7f;

{% endhighlight %}

![](images/scaleoffset.png)

