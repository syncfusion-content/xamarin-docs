---
layout : post
title : Interaction in Syncfusion Carousel Control in Xamarin.
description : Learn how to perform an operation while changing the carouselItem or Collection in Carousel for Xamarin.
platform : Xamarin
control : Carousel
documentation : ug
---

# How to perform an operation while changing the carouselItem?

We can perform operation while changing the carouselItem using [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_SelectionChanged) event. [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_SelectionChanged) event returns the index and selected carouselItem

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
            SelectionChanged="Carousel_SelectionChanged"/>
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
                ItemWidth = 200
            };

            carousel.ItemTemplate = new DataTemplate(() =>
            {
                Image image = new Image();
                image.SetBinding(Image.SourceProperty, "Image");
                image.Aspect = Aspect.AspectFit;
                return image;
            });

            carousel.SelectionChanged += Carousel_SelectionChanged;
            carousel.SetBinding(SfCarousel.ItemsSourceProperty, "ImageCollection");
            this.Content = carousel;
        }

        private void Carousel_SelectionChanged(object sender, SelectionChangedEventArgs e)
        {
            int count = (sender as SfCarousel).SelectedIndex + 1;
            DisplayAlert("SelectionChanged", "Carousel item:" + count + " has Selected", "Ok");
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


