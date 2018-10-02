---
layout : post
title : Data Binding  in Syncfusion Carousel control in Xamarin.Forms.
description : This section describes how to bind the data sources to populate items in the carousel and binding data in template of the carousel items.
platform : Xamarin
control : Carousel
documentation : ug
---

# Populating Data

SfCarousel control, supports binding to different data sources such as IList Data Source, Observable Collection Data Source.

## Through Binding

Items can be populated in SfCarousel control through data source and applying custom template as explained below. 

### Create a Model with Data

SfCarousel items can be populated with a collection of image data. For example, a user may wants to create a SfCarousel control which will display a list of images.

The SfCarousel model looks as follows.

{% highlight C# %}

public class CarouselModel
{
	public CarouselModel(string imageString)
	{
		Image = imageString;
	}
	private string _image;
	public string Image
	{
		get { return _image; }
		set { _image = value; }
	}
}

{% endhighlight %}

Populate carousel items collection in View model with the image data. The below code works when the images are placed within the application folder for Android, iOS and UWP with build action Android Resource, Bundled Resource and Content respectively.

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

N> Images can also be referred in PCL and from website URL as [instructed](https://developer.xamarin.com/guides/xamarin-forms/working-with/images/)


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

Different set of views can be provided to every items through `ItemContent` property available in SfCarouselItem class.

{% highlight C# %}

SfCarousel carousel = new SfCarousel();

ObservableCollection<SfCarouselItem> listOf = new ObservableCollection<SfCarouselItem>();

listOf.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "image1.png",Aspect=Aspect.Fill } });
listOf.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "image2.png",Aspect=Aspect.Fill } });
listOf.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "image3.png",Aspect=Aspect.Fill } });
listOf.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "image4.png",Aspect=Aspect.Fill } });
listOf.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "image5.png",Aspect=Aspect.Fill } });

carousel.DataSource = listOf;

this.Content = carousel;	

	  
{% endhighlight %}

and also carousel provides a support to display only the Image data with `Image` property in SfCarouselItem class.

{% highlight C# %}

public partial class CarouselControlPage : ContentPage
{
        public CarouselControlPage()
        {
            InitializeComponent();

            SfCarousel carousel = new SfCarousel() { ItemWidth = 170, ItemHeight = 250 };

            ObservableCollection<SfCarouselItem> collectionOfItems = new ObservableCollection<SfCarouselItem>();

            collectionOfItems.Add(new SfCarouselItem() { ImageName = "images1.png" });
            collectionOfItems.Add(new SfCarouselItem() { ImageName = "images2.png" });
            collectionOfItems.Add(new SfCarouselItem() { ImageName = "images3.png" });
            collectionOfItems.Add(new SfCarouselItem() { ImageName = "images4.png" });
            collectionOfItems.Add(new SfCarouselItem() { ImageName = "images5.png" });
            collectionOfItems.Add(new SfCarouselItem() { ImageName = "images6.png" });

            carousel.DataSource = collectionOfItems;

            this.Content =carousel;
        }
}	

{% endhighlight %}


Similar way every item can be created and customized in case of different carousel item view is needed.


