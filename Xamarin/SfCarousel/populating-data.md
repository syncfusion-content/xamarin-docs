---
layout : post
title : Populating data in Syncfusion Carousel control in Xamarin.Forms.
description : Learn how to set the ItemsSource in Carousel for Xamarin.Forms.
platform : Xamarin
control : Carousel
documentation : ug
---

# Populating Data

## ItemSource

SfCarousel items can be populated with a collection of image data. For example, a user may wants to create a SfCarousel control which will display a list of images.

The SfCarousel model looks as follows.

{% highlight C# %}

	public CarouselModel(string imagestr)
        {
            Image = imagestr;
        }
        private string _image;

        public string Image
        {
            get { return _image; }
            set { _image = value; }
        }

{% endhighlight %}

Create and populate SfCarousel collection as follows

{% highlight C# %}

	carousel.DataSource = GetDataSource();
	List<CarouselModel> GetDataSource()
    {
	List<CarouselModel> list = new List<CarouselModel>();

	list.Add(new CarouselModel("image1.png"));
    list.Add(new CarouselModel("image2.png"));
	list.Add(new CarouselModel("image3.png"));
    list.Add(new CarouselModel("image4.png"));
    list.Add(new CarouselModel("image5.png"));
	}

{% endhighlight %}

## ItemTemplate

SfCarousel contents can be customized by using `ItemTemplate` property. Through the ItemTemplate user can set up data bindings to the user objects.


{% highlight xaml %}

	<ResourceDictionary>
      <DataTemplate x:Key="itemTemplate">
        <Image Source="{Binding Image}"  Aspect="AspectFit"/>
      </DataTemplate>
    </ResourceDictionary>
	
	<carousel:SfCarousel x:Name="carousel" ItemTemplate="{StaticResource itemTemplate}" HeightRequest="600" WidthRequest="400" />

{% endhighlight %}

## SelectedIndex

It gets or sets the Selected Item index value of SfCarousel control to bring the particular item to center of the screen.

N> The `SelectedIndex` property will be 0 by default

{% tabs %}

{% highlight C# %}

	carousel.SelectedIndex=2;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" SelectedIndex="2" />
	
{% endhighlight %}

{% endtabs %}

