---
layout: post
title: Getting Started with Xamarin Carousel View control | Syncfusion
description: Learn here about getting started with Syncfusion Xamarin Carousel View (SfCarousel) control, its elements and more.
platform: Xamarin
control: Carousel
documentation: ug
---

# Getting Started with Xamarin Carousel View (SfCarousel)

This section explains how to showcase a Gallery of photos along with a Title using [Xamarin Carousel View](https://www.syncfusion.com/xamarin-ui-controls/xamarin-carousel-view) (SfCarousel) Control.

## Assembly deployment

After installing [Essential Studio for Xamarin](https://www.syncfusion.com/downloads/xamarin), you can find all the required assemblies in the installation folders, {Syncfusion Essential Studio Installed location} \Essential Studio\\{Version #}\Xamarin\lib.

E.g.: C:\Program Files (x86) \Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib

N> Assemblies can be found in unzipped package location(Documents/Syncfusion/{Version #}/Xamarin/lib) in Mac.

## Adding SfCarousel reference

You can add [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) reference using one of the following methods:

**Method 1: Adding SfCarousel reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfCarousel](https://www.nuget.org/packages/Syncfusion.Xamarin.SfCarousel), and then install it.

![Adding SfCarousel reference from NuGet](images/Adding SfCarousel reference.png)

N> Install the same version of [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) NuGet in all the projects.

**Method 2: Adding SfCarousel reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

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
<td>Syncfusion.SfCarousel.XForms.Android.dll<br/>Syncfusion.SfCarousel.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
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

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/installation/mac-installer/how-to-download) and [Windows](https://help.syncfusion.com/xamarin/installation/web-installer/how-to-download).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/overview) to know about registering Syncfusion license key in your Xamarin application to use our components.


## Launching the SfCarousel on each platform

To use [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) inside an application, each platform application must initialize the [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android and  UWP

The Android and UWP launches the [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application

N> If you are adding the references from toolbox, this step is not needed.

### iOS

To launch the [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) in iOS, call the `SfCarouselRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework has been initialized and before the LoadApplication is called, as demonstrated in the following code example.


{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
	global::Xamarin.Forms.Forms.Init();

	Syncfusion.SfCarousel.XForms.iOS.SfCarouselRenderer.Init();

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

The Xamarin Carousel View (SfCarousel) control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"

{% endhighlight %}

{% highlight C# %}

	using Syncfusion.SfCarousel.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"
             xmlns:local="clr-namespace:CarouselSample"
             x:Class="CarouselSample.MainPage">
    <carousel:SfCarousel x:Name="carousel" />
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfCarousel.XForms;
using Xamarin.Forms;

namespace CarouselSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfCarousel carousel = new SfCarousel();
            this.Content = carousel;
        }
    }
}

{% endhighlight %}

{% endtabs %}


## Add Carousel Items

We can populate the carousel's items by using any one of the following ways,

* Through [`SfCarouselItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarouselItem.html)

* Through [`ItemTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_ItemTemplate)

### Through SfCarouselItem

By passing the list of [`SfCarouselItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarouselItem.html) , we can get the view of [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control. In that we can pass Images as well as Item content.

The following code example illustrates to add list of Images in Carousel ,

{% highlight C# %}

using Syncfusion.SfCarousel.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace CarouselSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfCarousel carousel = new SfCarousel()
            {
                ItemWidth = 170,
                ItemHeight = 250
            };
            ObservableCollection<SfCarouselItem> carouselItems = new ObservableCollection<SfCarouselItem>();
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person1.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person2.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person3.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person4.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person5.png" });

            carousel.ItemsSource = carouselItems;

            this.Content = carousel;
        }
    }
}

{% endhighlight %}

The following code example illustrates to add list of Item in Carousel ,

{% highlight C# %}

using Syncfusion.SfCarousel.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace CarouselSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfCarousel carousel = new SfCarousel()
            {
                ItemWidth = 170,
                ItemHeight = 250
            };

            ObservableCollection<SfCarouselItem> carouselItems = new ObservableCollection<SfCarouselItem>();

            carouselItems.Add(new SfCarouselItem()
            {
                ItemContent = new Button()
                {
                    Text = "ItemContent1",
                    TextColor = Color.White,
                    BackgroundColor = Color.FromHex("#7E6E6B"),
                    FontSize = 12
                }
            });
            carouselItems.Add(new SfCarouselItem()
            {
                ItemContent = new Label()
                {
                    Text = "ItemContent2",
                    BackgroundColor = Color.FromHex("#7E6E6B"),
                    HorizontalTextAlignment = TextAlignment.Center,
                    VerticalTextAlignment = TextAlignment.Center,
                    FontSize = 12
                }
            });
            carouselItems.Add(new SfCarouselItem()
            {
                ItemContent = new Image()
                {
                    Source = "carousel_person1.png",
                    Aspect = Aspect.AspectFit
                }
            });

            carousel.ItemsSource = carouselItems;

            this.Content = carousel;
        }
    }
}


{% endhighlight %}

### Through ItemTemplate

[`ItemTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_ItemTemplate) property of Xamarin Carousel View (SfCarousel) control is used to customize the contents of [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) items.

* Create a model view which holds image data

{% highlight C# %}

namespace CarouselSample
{
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
}

{% endhighlight %}

* Populate carousel items collection in View model with the image data. 

{% highlight C# %}

using System.Collections.Generic;

namespace CarouselSample
{
    public class CarouselViewModel
    {
        public CarouselViewModel()
        {
            ImageCollection.Add(new CarouselModel("carousel_person1.png"));
            ImageCollection.Add(new CarouselModel("carousel_person2.png"));
            ImageCollection.Add(new CarouselModel("carousel_person3.png"));
            ImageCollection.Add(new CarouselModel("carousel_person4.png"));
            ImageCollection.Add(new CarouselModel("carousel_person5.png"));
        }
        private List<CarouselModel> imageCollection = new List<CarouselModel>();
        public List<CarouselModel> ImageCollection
        {
            get { return imageCollection; }
            set { imageCollection = value; }
        }
    }
}

{% endhighlight %}

The following code illustrates the way to use [`ItemTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_ItemTemplate) in both XAML as well as C#

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"
             xmlns:local="clr-namespace:CarouselSample"
             x:Class="CarouselSample.MainPage">
    <ContentPage.BindingContext>
        <local:CarouselViewModel/>
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
                             HeightRequest="400" 
                             WidthRequest="800" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfCarousel.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace CarouselSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            CarouselViewModel carouselViewModel = new CarouselViewModel();

            SfCarousel carousel = new SfCarousel()
            {
                HeightRequest = 400,
                WidthRequest = 800
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
            carousel.ItemsSource = carouselViewModel.ImageCollection;

            this.Content = carousel;
        }
    }

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

    public class CarouselViewModel
    {
        public CarouselViewModel()
        {
            ImageCollection.Add(new CarouselModel("carousel_person1.png"));
            ImageCollection.Add(new CarouselModel("carousel_person2.png"));
            ImageCollection.Add(new CarouselModel("carousel_person3.png"));
            ImageCollection.Add(new CarouselModel("carousel_person4.png"));
            ImageCollection.Add(new CarouselModel("carousel_person5.png"));
        }

        private List<CarouselModel> imageCollection = new List<CarouselModel>();
        public List<CarouselModel> ImageCollection
        {
            get { return imageCollection; }
            set { imageCollection = value; }
        }
    }
}

{% endhighlight %}
{% endtabs %}

I> Carousel's Images are placed within the application folder for Android, iOS and UWP with build action Android Resource, Bundled Resource and Content respectively. 

N> In addition, carousel provides a support to load the Images from `URL` and `SD Card` location.

## Setting the height and width of the carousel item

[`ItemHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_ItemHeight) and [`ItemWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_ItemWidth) properties are used to change the height and width of carouselItem in carousel panel.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"
             xmlns:local="clr-namespace:CarouselSample"
             x:Class="CarouselSample.MainPage">
    <carousel:SfCarousel x:Name="carousel"
                         ItemHeight="170"
                         ItemWidth="270"/>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfCarousel.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace CarouselSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfCarousel carousel = new SfCarousel()
            {
                ItemWidth = 170,
                ItemHeight = 250
            };

            ObservableCollection<SfCarouselItem> carouselItems = new ObservableCollection<SfCarouselItem>();
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person1.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person2.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person3.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person4.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person5.png" });

            carousel.ItemsSource = carouselItems;

            this.Content = carousel;
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Set Desire Item to be Selected

We can bring particular item to the center of the screen using [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_SelectedIndex) property in [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control.

The items can be populated as described [above](#add-carousel-items)

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"
             xmlns:local="clr-namespace:CarouselSample"
             x:Class="CarouselSample.MainPage">
    <carousel:SfCarousel x:Name="carousel"
                         ItemHeight="170"
                         ItemWidth="270"
                         SelectedIndex="2"/>
</ContentPage>
	
{% endhighlight %}

{% highlight C# %}

using Syncfusion.SfCarousel.XForms;
using System.Collections.ObjectModel;
using Xamarin.Forms;

namespace CarouselSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfCarousel carousel = new SfCarousel()
            {
                ItemWidth = 170,
                ItemHeight = 250,
                SelectedIndex = 2
            };

            ObservableCollection<SfCarouselItem> carouselItems = new ObservableCollection<SfCarouselItem>();
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person1.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person2.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person3.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person4.png" });
            carouselItems.Add(new SfCarouselItem() { ImageName = "carousel_person5.png" });

            carousel.ItemsSource = carouselItems;

            this.Content = carousel;
        }
    }
}

{% endhighlight %}

{% endtabs %}

N> The [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_SelectedIndex) property will be 0 by default.

![OverView image for Carousel](images/gettingstarted.png)

You can find the complete getting started sample from this [link.](https://github.com/SyncfusionExamples/xamarin-forms-sfcarousel)