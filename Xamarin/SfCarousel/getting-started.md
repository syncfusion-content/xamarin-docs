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

## Adding SfCarousel reference

You can add SfCarousel reference using one of the following methods:

**Method 1: Adding SfCarousel reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfCarousel to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfCarousel](https://www.nuget.org/packages/Syncfusion.Xamarin.SfCarousel), and then install it.

![Adding SfCarousel reference from NuGet](images/Adding SfCarousel reference.png)

N> Install the same version of SfCarousel NuGet in all the projects.

**Method 2: Adding SfCarousel reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfCarousel control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfCarousel assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfCarousel.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfCarousel.Android.dll<br/>Syncfusion.SfCarousel.XForms.Android.dll<br/>Syncfusion.SfCarousel.XForms.dll<br/>Xamarin.Android.Support.v17.Leanback (from NuGet Packages)<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfCarousel.iOS.dll<br/>Syncfusion.SfCarousel.XForms.iOS.dll<br/>Syncfusion.SfCarousel.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfCarousel.UWP.dll<br/>Syncfusion.SfCarousel.XForms.UWP.dll<br/>Syncfusion.SfCarousel.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.


## Launching the SfCarousel on each platform

To use SfCarousel inside an application, each platform application must initialize the SfCarousel renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android and  UWP

The Android and UWP launches the SfCarousel without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch SfCarousel in iOS, need to create an instance of SfCarouselRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below.


{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
	global::Xamarin.Forms.Forms.Init();

	new SfCarouselRenderer();

	LoadApplication(new App());

	return base.FinishedLaunching(app, options);
}

{% endhighlight %}

### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the SfCarousel assemblies in `App.xaml.cs` in UWP project as like in below code snippet.

{% highlight C# %}

// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
…

	rootFrame.NavigationFailed += OnNavigationFailed;
		
	// you'll need to add `using System.Reflection;`
	List<Assembly> assembliesToInclude = new List<Assembly>();

	//Now, add all the assemblies your app uses
	assembliesToInclude.Add(typeof(SfCarouselRenderer).GetTypeInfo().Assembly);

	// replaces Xamarin.Forms.Forms.Init(e);        
	Xamarin.Forms.Forms.Init(e, assembliesToInclude);
		
…     
}
{% endhighlight %}
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

### Through SfCarouselItem

By passing the list of `SfCarouselItem` , we can get the view of SfCarousel control. In that we can pass Images as well as Item content.

The following code example illustrates to add list of Images in Carousel ,

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

            carousel.ItemsSource = collectionOfItems;

            this.Content =carousel;
        }
}	


{% endhighlight %}

The following code example illustrates to add list of Item in Carousel ,

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

			carousel.ItemsSource = collectionOfItems;

            this.Content =carousel;
        }
}	


{% endhighlight %}

### Through ItemTemplate

`ItemTemplate` property of SfCarousel control is used to customize the contents of SfCarousel items.

* Create a model view which holds image data

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

* Populate carousel items collection in View model with the image data. 

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

The following code illustrates the way to use `ItemTemplate` in both XAML as well as C#

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
		<syncfusion:SfCarousel x:Name="carousel"  ItemTemplate="{StaticResource itemTemplate}" ItemsSource="{Binding ImageCollection}"  HeightRequest="400" WidthRequest="800" />	
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
			carousel.ItemsSource = ImageCollection;

            this.Content = carousel;
        }
    }

{% endhighlight %}


{% endtabs %}

* Finally set the `BindingContext` for the items collection in code behind.

{% highlight C# %}

carousel.BindingContext = new CarouselViewModel();

{% endhighlight %}

I> Carousel's Images are placed within the application folder for Android, iOS and UWP with build action Android Resource, Bundled Resource and Content respectively. 

N> In addition, carousel provides a support to load the Images from `URL` and `SD Card` location.

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


## Setting the height and width of carousel's Item

`ItemHeight` and `ItemWidth` properties are used to change the height and width of carouselItem in carousel panel.

{% highlight C# %}

SfCarousel sfCarousel=new SfCarousel();
sfCarousel.ItemWidth=150;
sfCarousel.ItemHeight=170;

{% endhighlight %}

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

![OverView image for Carousel](images/gettingstarted.png)

You can find the complete getting started sample from this [link.](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted982303964.zip)