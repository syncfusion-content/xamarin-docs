---
layout: post
title: Swipe Events in Xamarin Carousel View Control | Syncfusion
description: Explore the swipe events supported by the Syncfusion Xamarin Carousel View (SfCarousel) control.
platform: Xamarin
control: SfCarousel
documentation: ug
---

# Swipe Events in Xamarin Carousel View (SfCarousel)

## Swipe Start

The [`SwipeStarted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_SwipeStarted) event is triggered when a swipe gesture begins.

[`SwipeStartedEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SwipeStartedEventArgs.html) includes the [`IsSwipeLeft`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SwipeStartedEventArgs.html#Syncfusion_SfCarousel_XForms_SwipeStartedEventArgs_IsSwipedLeft) property, indicating whether the swipe direction is from the left side.

## Swipe End

The [`SwipeEnded`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_SwipeEnded) event is triggered when swiping completes on the carousel items.

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
            SwipeStarted="carousel_SwipeStarted"
            SwipeEnded="carousel_SwipeEnded"
			ItemTemplate="{StaticResource itemTemplate}"
			ItemsSource="{Binding ImageCollection}"
			ItemHeight="200"
			ItemWidth="200"
			ItemSpacing="2"
			AllowLoadMore="True"
			ViewMode="Linear">
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
                AllowLoadMore = true,
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

        private async void carousel_SwipeStarted(object sender, Syncfusion.SfCarousel.XForms.SwipeStartedEventArgs e)
        {
          // Trigger when swipe starts in the carousel item.
        }

         private async void carousel_SwipeEnded(object sender, EventArgs e)
        {
           // Trigger before swipe ends in the carousel item.
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

N> The [`SwipeStarted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_SwipeStarted) and [`SwipeEnded`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_SwipeEnded) events are supported on Android and iOS platforms only.

![Carousel Swiping events](images/CarouselSwiping_GIF.gif)
