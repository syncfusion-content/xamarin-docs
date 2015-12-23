---
layout : post
title : Data source in Syncfusion Carousel control in Xamarin.Forms.
description : Learn how to set the Data source in Carousel for Xamarin.Forms.
platform : Xamarin
control : Carousel
documentation : ug
---

SfCarousel items can be populated with a collection of business objects. For example, a user may want to create a SfCarousel control which will display a list of images.

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


