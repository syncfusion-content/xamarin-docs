---
layout : post
title : Interaction in Syncfusion Carousel Control in Xamarin.
description : Learn how to perform an operation while changing the carouselItem or Collection in Carousel for Xamarin.
platform : Xamarin
control : Carousel
documentation : ug
---

# How to perform an operation while changing the carouselItem?

We can perform operation while changing the carouselItem using `SelectionChanged` event. SelectionChanged event returns the index and selected carouselItem

{% highlight C# %}

sfCarousel.SelectionChanged+=(object sender, SelectionChangedEventArgs e) => 
{
    
};

{% endhighlight %}


