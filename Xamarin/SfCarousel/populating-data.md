---
layout : post
title : Populating data in Syncfusion Carousel control in Xamarin.Forms.
description : Learn how to set the ItemsSource in Carousel for Xamarin.Forms.
platform : Xamarin
control : Carousel
documentation : ug
---

# Populating Data

## ItemsSource

SfCarousel items can be populated with a collection of image datas. For example, a user may want to create a SfCarousel control which will display a list of images.

{% tabs %}

{% highlight C# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfCarouselItem item =new SfCarouselItem();
	item.Image="image"+i;
	temp.add(item);
	}
	carousel.ItemsSource=temp;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" ItemsSource="temp" />
	
{% endhighlight %}

{% endtabs %}

## SelectedIndex

It gets or sets the Selected Item index value of carousel control to bring the particular item to center of the screen.

N> The selectedIndex property will be 0 by default

{% tabs %}

{% highlight C# %}

	carousel.SelectedIndex=2;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" SelectedIndex="2" />
	
{% endhighlight %}

{% endtabs %}

