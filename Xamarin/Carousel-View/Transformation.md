---
layout : post
title: Transformation in Xamarin Carousel View control | Syncfusion
description: Learn here all about Transformation support in Syncfusion Xamarin Carousel View (SfCarousel) control and more.
platform : xamarin
control : Carousel
documentation : ug
---

# Transformation in Xamarin Carousel View (SfCarousel)

The [`Offset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_Offset) between selected and unselected item can be customized in  [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control. And also the items can be scaled to the specified value.

## Tilt Non Selected Items

The [`RotationAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_RotationAngle) property in the  [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control is used to tilt all the unselected items in a specified angle. 

N> If the angle value is positive, then the rotation is in the clockwise direction. If the angle value is negative, the rotation is in the counterclockwise direction. 

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
                         RotationAngle="90"/>
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
                RotationAngle = 90
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

![Rotation angle](images/rotationangle.png)


## Set Gap between Items

The [`Offset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_Offset) property is used to specify the accurate distance between unselected items in  [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) panel.  

N> The default value is 20.

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
                         Offset="30"/>
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
                Offset = 30
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

![offset](images/offset.png)

## Set Gap between Selected and unselected Item

Distance between the selected item and other items can be customized by using [`SelectedItemOffset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_SelectedItemOffset) property of the  [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control.

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
                         SelectedItemOffset="5"/>
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
                SelectedItemOffset = 5
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

## Set Scaling for Carousel Items

The [`ScaleOffset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_ScaleOffset) property in the  [`SfCarousel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html) control is used to scale all the items to the specified scale value.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"
             xmlns:local="clr-namespace:CarouselSample"
             x:Class="CarouselSample.MainPage">
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
            ScaleOffset="0.7"/>
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
            this.BindingContext = new CarouselViewModel();
            SfCarousel carousel = new SfCarousel()
            {
                ItemHeight = 200,
                ItemWidth = 200,
                ScaleOffset = 0.7f
            };

            carousel.ItemTemplate = new DataTemplate(() =>
            {
                Image image = new Image();
                image.SetBinding(Image.SourceProperty, "Image");
                image.Aspect = Aspect.AspectFit;
                return image;
            });

            carousel.SetBinding(SfCarousel.ItemsSourceProperty, "ImageCollection");
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

![Scale offset](images/scaleoffset.png)

## Spacing between the Items in Linear mode

Spacing of all the items in Linear mode can be determined by using [`ItemSpacing`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_ItemSpacing) property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"
             xmlns:local="clr-namespace:CarouselSample"
             x:Class="CarouselSample.MainPage">
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
			ItemSpacing="10"
			ViewMode="Linear"/>
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
            this.BindingContext = new CarouselViewModel();
            SfCarousel carousel = new SfCarousel()
            {
                ItemHeight = 200,
                ItemWidth = 200,
                ItemSpacing = 10,
                ViewMode = ViewMode.Linear
            };

            carousel.ItemTemplate = new DataTemplate(() =>
            {
                Image image = new Image();
                image.SetBinding(Image.SourceProperty, "Image");
                image.Aspect = Aspect.AspectFit;
                return image;
            });

            carousel.SetBinding(SfCarousel.ItemsSourceProperty, "ImageCollection");
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

