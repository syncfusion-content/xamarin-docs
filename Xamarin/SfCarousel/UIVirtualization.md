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

* EnableVirtualization  

## EnableVirtualization

UI Virtualization concept is achieved by enabling the EnableVirtualization property.

N> The default value of the EnableVirtualization property is false.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:local="clr-namespace:LoadMore"
    x:Class="LoadMore.MainPage"
    xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms">

<ContentPage.BindingContext>
  <local:CarouselViewModel />
</ContentPage.BindingContext>

	<ContentPage.Resources>
		<ResourceDictionary>
			<DataTemplate x:Key="itemTemplate">
				<Image Source="{Binding Image}"
				Aspect="AspectFit"/>
			</DataTemplate>
		</ResourceDictionary>
	</ContentPage.Resources>

	<ContentPage.Content>
		<carousel:SfCarousel x:Name="carousel"
			ItemTemplate="{StaticResource itemTemplate}"
			ItemsSource="{Binding ImageCollection}"
			ItemHeight="200"
			ItemWidth="200"
			ItemSpacing="2"
			EnableVirtualization="True"
			ViewMode="Linear">
		</carousel:SfCarousel>
	</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

SfCarousel carousel = new SfCarousel();

this.BindingContext = new CarouselViewModel();

carousel.ItemTemplate = new DataTemplate(() => {
                Image image = new Image();
                image.SetBinding(Image.SourceProperty, "Image");
                image.Aspect = Aspect.AspectFit;
                return image;
            });

carousel.SetBinding(SfCarousel.ItemsSourceProperty, "ImageCollection");

carousel.ItemHeight = 100;

carousel.ItemWidth = 100;

carousel.ItemSpacing = 2;
            
//Enable Virtualization in SfCarousel
           
 carousel.EnableVirtualization = true;

{% endhighlight %}

{% endtabs %}

![](images/UIVirtualization.png)

You can find the complete UIVirtualization sample from this [link.](http://www.syncfusion.com/downloads/support/forum/137855/ze/UIVirtualization618680329)