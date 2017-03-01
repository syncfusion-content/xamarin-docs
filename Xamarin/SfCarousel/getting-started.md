---
layout : post
title : Getting Started with Syncfusion Carousel control for Xamarin.Forms
description : A quick tour to initial users on Syncfusion Carousel control for Xamarin.Forms platform.
platform : Xamarin
control : Carousel
documentation : ug
---

# Getting Started

This section explains how to showcase a Gallery of photos along with a Title using SfCarousel Control.

## Add SfCarousel reference

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfchart) link to know about the assemblies required for adding Carousel to your project.

## Launching the SfCarousel on each platform

To use SfCarousel inside an application, each platform application must initialize the SfCarousel renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android and  UWP

The Android and UWP launches the SfCarousel without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application

### iOS

To launch SfCarousel in iOS, need to create an instance of SfCarouselRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below.

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
	global::Xamarin.Forms.Forms.Init();

	new SfCarouselRenderer();

	LoadApplication(new App());

	return base.FinishedLaunching(app, options);
}

{% endhighlight %}

{% endtabs %}

## Create a Simple SfCarousel 

The SfCarousel control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfCarousel and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	xmlns:syncfusion="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"

{% endhighlight %}

{% highlight C# %}

	using Syncfusion.SfCarousel.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the SfCarousel control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
		xmlns:syncfusion="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"
		x:Class="GettingStarted.CarouselControlPage">
  <ContentPage.Content>
     <syncfusion:SfCarousel x:Name="carousel" />	
	</ContentPage.Content>
	
</ContentPage>

{% endhighlight %}

{% highlight C# %}


using Syncfusion.SfCarousel.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
public partial class CarouselControlPage : ContentPage
    {
        public CarouselControlPage()
        {
            InitializeComponent();

            SfCarousel carousel = new SfCarousel();

            this.Content = carousel;
        }
    }
}

{% endhighlight %}

{% endtabs %}


## Add Carousel Items

We can populate the carousel's items by using any one of the following ways,

* Through SfCarouselItem

* Through ItemTemplate

## Through SfCarouselItem

By passing the list of `SfCarouselItem` , we can get the view of SfCarousel control. In that we can pass Images as well as Item content.

The following code example illustrates to add list of Images in Carousel ,


{% tabs %}

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

            carousel. DataSource = collectionOfItems;

            this.Content =carousel;


{% endhighlight %}

{% endtabs %}

The following code example illustrates to add list of Item in Carousel ,

{% tabs %}

{% highlight C# %}

	public partial class CarouselControlPage : ContentPage
    {
        public CarouselControlPage()
        {
            InitializeComponent();

            SfCarousel carousel = new SfCarousel() { ItemWidth = 170, ItemHeight = 250 };

            ObservableCollection<SfCarouselItem> collectionOfItems = new ObservableCollection<SfCarouselItem>();

			collectionOfItems.Add(new SfCarouselItem() { ItemContent = new Button() { Text = "ItemContent1",TextColor=Color.White, BackgroundColor = Color.FromHex("#7E6E6B"), FontSize = 12 } });
			collectionOfItems.Add(new SfCarouselItem() { ItemContent = new Label() { Text = "ItemContent2", BackgroundColor = Color.FromHex("#7E6E6B"), FontSize = 12 } });
			collectionOfItems.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "image1.png", Aspect = Aspect.AspectFit } });

			carousel.DataSource = collectionOfItems;

            this.Content =carousel;


{% endhighlight %}

{% endtabs %}

## Through ItemTemplate

`ItemTemplate` property of SfCarousel control is used to customize the contents of SfCarousel items and the data source collection has been bound to it.

* Create a model view which holds image data

{% tabs %}

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

{% endtabs %}

* Populate carousel items collection in View model with the image data. 

{% tabs %}

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

{% endtabs %}


The following code illustrates the way to use `ItemTemplate` in both xaml as well as c#

{% tabs %}

{% highlight xaml %}

	<ContentPage.Resources>
    	<ResourceDictionary>
     	 	<DataTemplate x:Key="itemTemplate">
       	 		<Image Source="{Binding Image}" Aspect="AspectFit"/>
      		</DataTemplate>
    	</ResourceDictionary>
 	 </ContentPage.Resources>

	<ContentPage.Content>
		<syncfusion:SfCarousel x:Name="carousel"  ItemTemplate="{StaticResource itemTemplate}" DataSource="{Binding ImageCollection}"  HeightRequest="400" WidthRequest="800" />	
	</ContentPage.Content>

{% endhighlight %}

{% highlight C# %}

public partial class CarouselControlPage : ContentPage
    {
        public CarouselControlPage()
        {
            InitializeComponent();

            SfCarousel carousel = new SfCarousel() {HeightRequest=400,WidthRequest=800};

             var ImageCollection = new List<CarouselModel> {
	  			new CarouselModel ("image1.png"),
				new CarouselModel ("image2.png"),
				new CarouselModel ("image3.png"),
				new CarouselModel ("image4.png"),
				new CarouselModel ("image5.png")
			};
			var itemTemplate = new DataTemplate(() =>
			{
				var grid = new Grid();
				var nameLabel = new Image();
				nameLabel.SetBinding(Image.SourceProperty, "Image");
				grid.Children.Add(nameLabel);
				return grid;
			});

			carousel.ItemTemplate = itemTemplate;
			carousel.DataSource = ImageCollection;

            this.Content = carousel;
        }
    }

{% endhighlight %}


{% endtabs %}

* Finally set the `BindingContext` for the items collection in code behind.

{% tabs %}

{% highlight C# %}

	carousel.BindingContext = new CarouselViewModel();

{% endhighlight %}

{% endtabs %}

N> Carousel's Images are placed within the application folder for Android, iOS and UWP with build action Android Resource, Bundled Resource and Content respectively. In addition, carousel provides a support 

to load the Images from `URL` and `SD Card` location.

## Set Gap between Items

SfCarousel provides option to set the distance between the unselected items in the panel. This can be done by using the `Offset` property in SfCarousel control. 

The items can be populated as described [above](#add-carousel-items)

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfCarousel x:Name="carousel" Offset="20"/>
	
{% endhighlight %}

{% highlight C# %}

	SfCarousel carousel = new SfCarousel();	
	carousel.Offset=20;

{% endhighlight %}

{% endtabs %}


## Tilt Non Selected Items

Items in the SfCarousel control can be rotated in user defined angle. `RotationAngle` property is used to decide the angle in which items should be rotated.

The items can be populated as described [above](#add-carousel-items)

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfCarousel x:Name="carousel" Offset="20" RotationAngle="45" />
	
{% endhighlight %}

{% highlight C# %}

	SfCarousel carousel = new SfCarousel();
	carousel.Offset=20;
	carousel.RotationAngle = 45;

{% endhighlight %}

{% endtabs %}

## Set Desire Item to be Selected

We can bring particular item to the center of the screen using `SelectedIndex` property in SfCarousel control.

The items can be populated as described [above](#add-carousel-items)

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfCarousel x:Name="carousel" Offset="20" RotationAngle="45" SelectedIndex="2" />
	
{% endhighlight %}

{% highlight C# %}

	SfCarousel carousel = new SfCarousel();
	carousel.Offset=20;
	carousel.RotationAngle = 45;
	carousel.SelectedIndex=2;

{% endhighlight %}

{% endtabs %}

N> The `SelectedIndex` property will be 0 by default.

![](images/gettingstarted.png)