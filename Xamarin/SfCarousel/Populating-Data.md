---
layout : post
title : Data Binding  in Syncfusion Carousel control in Xamarin.Forms.
description : Learn how to set the ItemsSource in Carousel for Xamarin.Forms.
platform : Xamarin
control : Carousel
documentation : ug
---

# Populating Data

SfCarousel control, supports binding to different data sources such as IList Data Source, Observable Collection Data Source.

## Through Binding

### Create a Model with Data

SfCarousel items can be populated with a collection of image data. For example, a user may wants to create a SfCarousel control which will display a list of images.

The SfCarousel model looks as follows.

{% highlight C# %}

	 public class CarouselModel
	 {
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
	}

{% endhighlight %}

Populate carousel items collection in Viewmodel with the image data. The below code works when the images are placed within the application folder for Android,iOS and UWP with build action AndroidResource,BundledResource and Content respectively.

{% highlight C# %}

	public class CarouselViewModel
	{
		public CarouselViewModel()
		{
			ImageCollection.Add(new CarouselModel("image1.png"));
			ImageCollection.Add(new CarouselModel("image2.png"));
			ImageCollection.Add(new CarouselModel("image3.png"));
			ImageCollection.Add(new CarouselModel("image4.png"));
			ImageCollection.Add(new CarouselModel("image5.png"));
		}
		private List<CarouselModel> imageCollection = new List<CarouselModel>();

		public List<CarouselModel> ImageCollection
		{
			get { return imageCollection; }
			set { imageCollection = value; }
		}
	}
{% endhighlight %}

N> Images can also be referred in PCL and from website url as [instructed](https://developer.xamarin.com/guides/xamarin-forms/working-with/images/)


### Binding the Data with Custom Template

SfCarousel provides support to add a custom view as carousel items by designing a view inside its ItemTemplate. This template will be applied for all its items and its data will be binded.


{% highlight xaml %}

	<ContentPage.Resources>
    	<ResourceDictionary>
     	 	<DataTemplate x:Key="itemTemplate">
       	 		<Image Source="{Binding Image}" 
					Aspect="AspectFit"/>
      		</DataTemplate>
    	</ResourceDictionary>
 	 </ContentPage.Resources>

	<ContentPage.Content>
		<carousel:SfCarousel x:Name="carousel"  ItemTemplate="{StaticResource itemTemplate}" DataSource="{Binding ImageCollection}"   HeightRequest="400" WidthRequest="800" />	
	</ContentPage.Content>
{% endhighlight %}

* Now set the `BindingContext` for the items collection in code behind.

{% highlight C# %}

	carousel.BindingContext = new CarouselViewModel();

{% endhighlight %}



## Through Carousel Item

The ItemTemplate provides common template with different data, whereas if different views for every items is needed, it can also be provided using `ItemContent` property in SfCarouselItem class.

{% highlight C# %}

	SfCarousel carousel = new SfCarousel();

			SfCarouselItem carouselItem = new SfCarouselItem();
			Label lbl = new Label();
			lbl.Text = "  Item No: 1 ";
			lbl.BackgroundColor = Color.Gray;
			lbl.FontSize = 25;
			lbl.VerticalTextAlignment = TextAlignment.Center;
			carouselItem.ItemContent = lbl;
			carousel.ItemsSource.Add(carouselItem);

			SfCarouselItem carouselItem1 = new SfCarouselItem();
			Image img = new Image();
			img.Source = ImageSource.FromFile("image2.png");
			img.Aspect = Aspect.AspectFit;
			img.VerticalOptions = LayoutOptions.Center;
			img.HeightRequest = 400;
			img.WidthRequest = 400;
			carouselItem1.ItemContent = img;
			carousel.ItemsSource.Add(carouselItem1);

			this.Content = carousel;	
	
	  
{% endhighlight %}

Similar way every item can be created and customized in case of different carousel item view is needed.


