---
layout: post
title: Getting Started with syncfusion Rotator control for Xamarin.Forms 
description:  A quick tour to initial users on Syncfusion Rotator control for Xamarin.Forms platform
platform: xamarin 
control: Rotator
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfRotator control in a real-time scenario and also provides a walk-through on some of the customization features available in SfRotator control.

## Add SfRotator reference

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfchart) link to know about the assemblies required for adding SfRotator to your project.

## Launching the SfRotator on each platform

To use SfRotator inside an application, each platform application must initialize the SfRotator renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android and  UWP

The Android and UWP launches the SfRotator without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application

### iOS

To launch SfRotator in iOS, need to create an instance of SfRotatorRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below.

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
	global::Xamarin.Forms.Forms.Init();

	new SfRotatorRenderer();

	LoadApplication(new App());

	return base.FinishedLaunching(app, options);
}	

{% endhighlight %}

{% endtabs %}

### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the SfRotator assemblies in `App.xaml.cs` in UWP project as like in below code snippet.

{% highlight C# %}

// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
…

	rootFrame.NavigationFailed += OnNavigationFailed;
		
	// you'll need to add `using System.Reflection;`
	List<Assembly> assembliesToInclude = new List<Assembly>();

	//Now, add all the assemblies your app uses
	assembliesToInclude.Add(typeof(SfRotatorRenderer).GetTypeInfo().Assembly);

	// replaces Xamarin.Forms.Forms.Init(e);        
	Xamarin.Forms.Forms.Init(e, assembliesToInclude);
		
…     
}
{% endhighlight %}

## Create a Simple SfRotator 

The SfRotator control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfRotator and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight C# %}

	using Syncfusion.SfRotator.XForms; 

{% endhighlight %}

{% highlight xaml %}

	xmlns:rotator="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
	
{% endhighlight %}

{% endtabs %}

* Now add the SfRotator control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
	xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
	xmlns:local="clr-namespace:GettingStarted" 
	xmlns:syncfusion="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"
	x:Class="GettingStarted.RotatorControlPage">
<ContentPage.Content>
 <syncfusion:SfRotator x:Name="rotator" />	
</ContentPage.Content>
</ContentPage>
	
	
{% endhighlight %}

{% highlight C# %}		

using Syncfusion.SfRotator.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
public partial class RotatorControlPage : ContentPage
    {
        public RotatorControlPage()
        {
            InitializeComponent();

            SfRotator rotator = new SfRotator();

            this.Content = rotator;
        }
    }
}
	
{% endhighlight %}

{% endtabs %}


## Add Rotator Items

We can populate the rotator's items by using any one of the following ways,

* Through SfRotatorItem

* Through ItemTemplate

### Through SfRotatorItem

By passing the list of `SfRotatorItem` , we can get the view of SfRotator control. In that we can pass Images as well as Item content.

The following code example illustrates to add list of Images in Carousel ,

{% tabs %}

{% highlight C# %}

public partial class RotatorControlPage : ContentPage
{
	public RotatorControlPage()
	{
		InitializeComponent();

		SfRotator rotator = new SfRotator();

		List<SfRotatorItem> collectionOfItems = new List<SfRotatorItem>();
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie1.png" });
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie2.png" });
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie3.png" });
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie4.png" });
		collectionOfItems.Add(new SfRotatorItem() { Image = "movie5.png" });

		rotator.DataSource = collectionOfItems;
		this.Content = rotator;

	}
}


{% endhighlight %}

{% endtabs %}

The following code example illustrates to add list of Item in Carousel ,

{% tabs %}

{% highlight C# %}

public partial class RotatorControlPage : ContentPage
{
	public RotatorControlPage()
	{
		InitializeComponent();

		SfRotator rotator = new SfRotator();
		List<SfRotatorItem> collectionOfItems = new List<SfRotatorItem>();
		collectionOfItems.Add(new SfRotatorItem() { ItemContent = new Button() { Text = "ItemContent1", TextColor = Color.White, BackgroundColor = Color.FromHex("#7E6E6B"), FontSize = 12 } });
		collectionOfItems.Add(new SfRotatorItem() { ItemContent = new Label() { Text = "ItemContent2", BackgroundColor = Color.FromHex("#7E6E6B"), FontSize = 12 } });
		collectionOfItems.Add(new SfRotatorItem() { ItemContent = new Image() { Source = "image1.png", Aspect = Aspect.AspectFit } });

		rotator.DataSource = collectionOfItems;
		this.Content = rotator;

	}
}

{% endhighlight %}

{% endtabs %}

### Through ItemTemplate

ItemTemplate property of SfRotator control is used to customize the contents of SfRotator items.ItemTemplate provides common template with different data.SfRotator items can be populated with a collection of image data. This collection includes Arrays, Lists and DataTables. For example you may wants to create a Rotator model with Image as follows.

{% tabs %}

{% highlight C# %}

public RotatorModel(string imageString)
{
    Image = imageString;
}
private String _image;
public String Image
{
    get { return _image; }
    set { _image = value; }
}

     
{% endhighlight %}

{% endtabs %}


Create and populate Rotator collection as follows

{% tabs %}

{% highlight C# %}

public RotatorViewModel()
{
    ImageCollection.Add(new RotatorModel("movie1.png"));
    ImageCollection.Add(new RotatorModel("movie2.png"));
    ImageCollection.Add(new RotatorModel("movie3.png"));
    ImageCollection.Add(new RotatorModel("movie4.png"));
    ImageCollection.Add(new RotatorModel("movie5.png"));
}
private List<RotatorModel> imageCollection = new List<RotatorModel>();

public List<RotatorModel> ImageCollection
{
    get { return imageCollection; }
    set { imageCollection = value; }
}

{% endhighlight %}

{% endtabs %}


{% tabs %}

{% highlight xaml %}

<syncfusion:SfRotator x:Name="rotator"  Grid.Row="0" NavigationDelay="2000" ItemsSource="{Binding ImageCollection}" SelectedIndex="2" NavigationDirection="Horizontal" NavigationStripMode="Dots" BackgroundColor="#ececec" NavigationStripPosition="Bottom">
<syncfusion:SfRotator.ItemTemplate>
  <DataTemplate>
    <Image  Source="{Binding Image}"/>                   
  </DataTemplate>
</syncfusion:SfRotator.ItemTemplate>
</syncfusion:SfRotator>
	  
{% endhighlight %}

{% highlight c# %}

public partial class RotatorControlPage : ContentPage
{
public RotatorControlPage()
{
	InitializeComponent();

	SfRotator rotator = new SfRotator();

	var ImageCollection = new List<RotatorModel> {
  			new RotatorModel ("image1.png"),
			new RotatorModel ("image2.png"),
			new RotatorModel ("image3.png"),
			new RotatorModel ("image4.png"),
			new RotatorModel ("image5.png")
		};
	var itemTemplate = new DataTemplate(() =>
	{
		var grid = new Grid();
		var nameLabel = new Image();
		nameLabel.SetBinding(Image.SourceProperty, "Image");
		grid.Children.Add(nameLabel);
		return grid;
	});

	rotator.ItemTemplate = itemTemplate;
	rotator.ItemSource = ImageCollection;

	this.Content = rotator;
}
}

{% endhighlight %}

{% endtabs %}

* Finally set the `BindingContext` for the items collection in code behind.

{% tabs %}

{% highlight C# %}

	rotator.BindingContext = new RotatorViewModel();

{% endhighlight %}

{% endtabs %}

I> Rotator's Images are placed within the application folder for Android, iOS and UWP with build action Android Resource, Bundled Resource and Content respectively. 

N> In addition, rotator provides a support to load the Images from `URL` and `SD Card` location.
 
## Setting Navigation Mode

SfRotator provides option to display the navigating items either in Thumbnail or Dots mode. The navigation mode for navigating items can be decided using `NavigationMode` property.

{% tabs %}

{% highlight C# %}	

SfRotator rotator = new SfRotator();
rotator.NavigationStripMode = NavigationStripMode.Dots;

{% endhighlight %}

{% highlight xaml %}

<syncfusion:SfRotator x:Name="rotator" NavigationStripMode="Dots" />
	
{% endhighlight %}

{% endtabs %}

## Customizing Position

The placement position of navigation strip items such as Thumbnail or Dots can be customized in SfRotator. This can be specified using `NavigationStripPosition` property.   

{% tabs %}

{% highlight C# %}	

SfRotator rotator = new SfRotator();
rotator.NavigationStripMode = NavigationStripMode.Dots;
rotator.NavigationStripPosition = NavigationStripPosition.Bottom;
	
{% endhighlight %}

{% highlight xaml %}

<syncfusion:SfRotator x:Name="rotator" NavigationStripMode="Dots"  NavigationStripPosition="Bottom"/>
	
{% endhighlight %}

{% endtabs %}

![](images/rotator.png)

You can find the complete getting started sample from this [link.](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted1493259513.zip)

