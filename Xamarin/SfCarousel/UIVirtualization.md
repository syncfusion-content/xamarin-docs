---
layout : post
title : UIVirtualization in Syncfusion Carousel control in Xamarin.Forms.
description : Learn how to set the UIVirtualization in Carousel for Xamarin.Forms.
platform : Xamarin
control : Carousel
documentation : ug
---

# UI Virtualization

In UI virtualization concept, only the number of items that can be adaptable to the viewport of our device are arranged. Even, if the numerous items have been added to the collection, it loads only the viewport adaptable count of the carousel Items. Items are added at the right of the view when swiping the countable items in forward direction. At the same time, same number of items are removed at the left of the view for maintaining the same viewport items count. Similarly, items are added at the left of the view when swiping in backward direction for maintaining the same viewport items count. At the time, the same number of items are removed at the right of the view. Using this mechanism, virtualization concept is achieved in the carousel control. 

The following property has been used in UIVirtualization support:

* IsVirtualizing  

## IsVirtualizing

UIvirtualization concept is achieved by enabling the IsVirtualizing property.

N> The default value of the IsVirtualizing property is false.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCarousel 
      x:Name="carousel"
      IsVirtualizing="True" />

{% endhighlight %}

{% highlight c# %}

SfCarousel carousel = new SfCarousel();

//Enable virtualization in SfCarousel

carousel.IsVirtualizing = true;

{% endhighlight %}

{% endtabs %}