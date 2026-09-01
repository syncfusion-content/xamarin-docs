---
layout: post
title: UI Virtualization in Xamarin Carousel View Control | Syncfusion
description: Discover the UI virtualization support in Syncfusion Xamarin Carousel View (SfCarousel) control.
platform: Xamarin
control: SfCarousel
documentation: ug
---

# UI Virtualization in Xamarin Carousel View (SfCarousel)

UI Virtualization allows the `SfCarousel` to efficiently manage resource usage by only rendering the number of items visible in the viewport. Even if a collection contains numerous items, only those that fit within the viewport are loaded. As users swipe forward, new items appear on the right, while an equal number of items are removed from the left to maintain the count. Similarly, when swiping backward, items are added from the left while the same number is removed from the right. This mechanism optimizes performance in the carousel control.

The primary property used for UI virtualization is:
* [`EnableVirtualization`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_EnableVirtualization)  

## EnableVirtualization

Enabling the [`EnableVirtualization`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_EnableVirtualization) property activates UI virtualization for the carousel view.

N> By default, the [`EnableVirtualization`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_EnableVirtualization) property is set to `false`.

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
            ItemSpacing="2"
			ViewMode="Linear"
            EnableVirtualization="true">
        </carousel:SfCarousel>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

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
                ItemSpacing = 2,
                EnableVirtualization = true,
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

![UI Virtualization](images/UIVirtualization.png)

Access the complete UI Virtualization sample from this [link](https://github.com/SyncfusionExamples/ui-virtualization-carousel).
