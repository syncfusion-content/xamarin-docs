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

SfCarousel provides support to add a custom view as Carouseltems by designing a view inside its ItemTemplate. This template will be applied for all its items and its data will be binded.


{% highlight xaml %}

	<ResourceDictionary>
      <DataTemplate x:Key="itemTemplate">
        <Image Source="{Binding Image}"  Aspect="AspectFit"/>
      </DataTemplate>
    </ResourceDictionary>
	
	<carousel:SfCarousel x:Name="carousel" ItemTemplate="{StaticResource itemTemplate}" HeightRequest="600" WidthRequest="400" />

{% endhighlight %}

## Setting variable views

The ItemTemplate provides common template with different data, whereas if different views for every items is needed, it can also be provided using `ItemContent` property in SfCarouselItem class.

{% highlight C# %}

	SfCarousel carousel = new SfCarousel();
	
	SfCarouselItem carouselItem = new SfCarouselItem ();
	Label lbl = new Label ();
	lbl.Text ="  Item No: 1 ";
	lbl.BackgroundColor = Color.Gray;
	lbl.FontSize = 20;
	lbl.VerticalTextAlignment = TextAlignment.Center;
	rotatorItem.ItemContent =lbl;
	carousel.DataSource.Add (carouselItem);	

	SfCarouselItem carouselItem1 = new SfCarouselItem ();
	Image img = new Image ();
	img.Source = ImageSource.FromFile("image2".png");
	img.Aspect = Aspect.AspectFit;
	img.VerticalOptions = LayoutOptions.Center;
	img.HeightRequest = 400;
	img.WidthRequest = 400;
	carouselItem1.ItemContent =img;
	carousel.DataSource.Add (carouselItem1);			
	
	  
{% endhighlight %}

Similar way every item can be created and customized in case of different carousel item view is needed.

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

