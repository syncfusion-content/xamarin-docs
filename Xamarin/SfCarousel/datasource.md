---
layout : post
title : Data source in Syncfusion Carousel control in Xamarin.Forms.
description : Learn how to populate the items in Carousel for Xamarin.Forms.
platform : Xamarin
control : Carousel
documentation : ug
---

# Populating Items

## DataSource

SfCarousel items can be populated with a collection of image data using `DataSource` property.

{% highlight C# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfCarouselItem item =new SfCarouselItem();
	item.ImageName="image";
	temp.add(item);
	}
	carousel.DataSource=temp;

{% endhighlight %}


