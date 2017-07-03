---
layout : post
title : Transformation in Syncfusion Carousel control in Xamarin.Forms
description : Learn how to set the Rotation Angle and Offset in Carousel for Xamarin.Forms
platform : Xamarin
control : Carousel
documentation : ug
---

# Transformation

The Offset between selected and unselected item can be customized in SfCarousel control. And also the items can be scaled to the specified value.

## Tilt Non Selected Items

The `RotationAngle` property in the SfCarousel control is used to tilt all the unselected items in a specified angle. 

N> If the angle value is positive, then the rotation is in the clockwise direction. If the angle value is negative, the rotation is in the counterclockwise direction. 

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCarousel x:Name="carousel" RotationAngle="90" />
	
{% endhighlight %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.RotationAngle = 90;
	
{% endhighlight %}

{% endtabs %}

![](images/rotationangle.png)


## Set Gap between Unselected Items

The `Offset` property is used to specify the accurate distance between unselected items in SfCarousel panel.  

N> The default value is 20.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCarousel x:Name="carousel" Offset="30" />
	
{% endhighlight %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.Offset=30;
	
{% endhighlight %}

{% endtabs %}

![](images/offset.png)

## Set Gap between Selected and unselected Item

Distance between the selected item and other items can be customized by using `SelectedItemOffset` property of the SfCarousel control.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCarousel x:Name="carousel" SelectedItemOffset="5" />
	
{% endhighlight %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.SelectedItemOffset=5;

{% endhighlight %}

{% endtabs %}

## Set Scaling for Carousel Items

The `ScaleOffset` property in the SfCarousel control is used to scale all the items to the specified scale value.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.ScaleOffset=0.7f;

{% endhighlight %}

![](images/scaleoffset.png)

## Spacing between the Items in Linear mode

Spacing of all the items in Linear mode can be determined by using `ItemSpacing` property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCarousel x:Name="carousel" ItemSpacing="10" ViewMode="Linear" />
	
{% endhighlight %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel();
carousel.ItemSpacing=5;
carousel.ViewMode=ViewMode.Linear;

{% endhighlight %}

{% endtabs %}

