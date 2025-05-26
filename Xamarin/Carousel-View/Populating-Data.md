---
layout: post
title: Populating Data in Xamarin Carousel View Control | Syncfusion
description: Discover how to populate data in the Syncfusion Xamarin Carousel View (SfCarousel) control.
platform: Xamarin
control: SfCarousel
documentation: ug
---

# Populating Data in Xamarin Carousel View (SfCarousel)

The [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control supports binding to various data sources, such as `IList` and `ObservableCollection`.

## Through Binding

Items can be populated in the [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control through data sources and by applying custom templates as explained below.

### Create a Data Model
[`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) items can be populated using a collection of image data. For instance, a user may want to create a [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control to display a list of images. Below is an example model:

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

Using the above model, populate the carousel items collection in the ViewModel with image data. This code works when images are placed within the application folder for Android, iOS, and UWP, with build actions Android Resource, Bundled Resource, and Content, respectively.

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

N> Images can also be referenced in PCL and from a website URL as [instructed here](https://developer.xamarin.com/guides/xamarin-forms/working-with/images/).

### Binding Data with a Custom Template

[`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) allows adding a custom view as carousel items by designing a view within its [`ItemTemplate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_ItemTemplate). This template is applied to all items.

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

- Set the `BindingContext` for the items collection in the code behind.

{% highlight C# %}

	carousel.BindingContext = new CarouselViewModel();

{% endhighlight %}

## Through Carousel Item

Different sets of views can be provided for each item using the [`ItemContent`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarouselItem.html#Syncfusion_SfCarousel_XForms_SfCarouselItem_ItemContent) property available in the [`SfCarouselItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarouselItem.html) class.

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

            carouselItems.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "carousel_person1.png", Aspect = Aspect.Fill } });
            carouselItems.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "carousel_person2.png", Aspect = Aspect.Fill } });
            carouselItems.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "carousel_person3.png", Aspect = Aspect.Fill } });
            carouselItems.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "carousel_person4.png", Aspect = Aspect.Fill } });
            carouselItems.Add(new SfCarouselItem() { ItemContent = new Image() { Source = "carousel_person5.png", Aspect = Aspect.Fill } });

            carousel.ItemsSource = carouselItems;

            this.Content = carousel;
        }
    }
}

{% endhighlight %}

Additionally, carousel provides support to display only the image data with the [`Image`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarouselItem.html#Syncfusion_SfCarousel_XForms_SfCarouselItem_ImageName) property in the [`SfCarouselItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarouselItem.html) class.

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

Each item can be customized for specific use cases requiring different views for carousel items.
