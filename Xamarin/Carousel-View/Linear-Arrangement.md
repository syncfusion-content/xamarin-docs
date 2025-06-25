---
layout: post
title: Linear Arrangement in Xamarin Carousel View Control | Syncfusion
description: Explore the linear arrangement support in Syncfusion Xamarin Carousel View (SfCarousel) control.
platform: Xamarin
control: SfCarousel
documentation: ug
---

# Linear Arrangement in Xamarin Carousel View (SfCarousel)

You can arrange carousel items in a stacked linear layout by setting the [`ViewMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.SfCarousel.html#Syncfusion_SfCarousel_XForms_SfCarousel_ViewMode) property to [`Linear`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.ViewMode.html#Syncfusion_SfCarousel_XForms_ViewMode_Linear). The default configuration uses [`Default`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCarousel.XForms.ViewMode.html#Syncfusion_SfCarousel_XForms_ViewMode_Default) mode.

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
                             WidthRequest="800"
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
            CarouselViewModel carouselViewModel = new CarouselViewModel();

            SfCarousel carousel = new SfCarousel()
            {
                HeightRequest = 400,
                WidthRequest = 800,
                ViewMode = ViewMode.Linear
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

N> For Android platform, include the Xamarin.Android.Support.v17.Leanback library to utilize carousel linear mode.

![Linear Mode](images/linear.png)
