---
layout : post
title : Populating data in Syncfusion Carousel control in Xamarin.Forms.
description : Learn how to set the DataSource in Carousel for Xamarin.Forms.
platform : Xamarin
control : Carousel
documentation : ug
---

# Populating Data

## DataSource

SfCarousel items can be populated with a collection of image datas. For example, a user may want to create a SfCarousel control which will display a list of images.

{% highlight C# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfCarouselItem item =new SfCarouselItem();
	item.ImageName="image"+i;
	temp.add(item);
	}
	carousel.DataSource=temp;

{% endhighlight %}

## SelectedIndex

It gets or sets the Selected Item index value of carousel control to bring the particular item to center of the screen.

N> The selectedIndex property will be 0 by default

{% highlight C# %}

	carousel.SelectedIndex=2;

{% endhighlight %}

