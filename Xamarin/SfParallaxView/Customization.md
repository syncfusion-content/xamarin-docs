---
layout: post
title: Syncfusion ParallaxView customization in Xamarin.Forms
description: How to customize the scrolling speed of the content added as a background view and content orientation.
platform: xamarin.forms
control: SfParallaxView
documentation: ug
---

## Customization

## Speed Customization

The `Speed` value denotes the scrolling speed of the `Content` added as a background view. Based on the speed value, the background view will scroll along with the foreground view.

{% tabs %}

{% highlight xaml %}

     <parallax:SfParallaxView Source="{x:Reference Name = listview}" x:Name="parallaxview" Speed="0.5" >
            <parallax:SfParallaxView.Content>
                <Image BackgroundColor="Transparent" Source="{Binding Image}" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
            </parallax:SfParallaxView.Content>
     </parallax:SfParallaxView>

{% endhighlight %}

{% highlight c# %}

using Xamarin.Forms;
using Syncfusion.XForms.ParallaxView;

namespace ParallaxView_GettingStarted
{
    public partial class MainPage : ContentPage
    {

        public MainPage()
        {
            InitializeComponent();
            SfParallaxView parallaxview = new SfParallaxView();
            SfListView listview = new SfListView();
            Image image = new Image();
            Assembly assembly = typeof(MainPage).GetTypeInfo().Assembly;
            image.Source = ImageSource.FromResource("ParallaxView_GettingStarted.Images.ParallaxWallpaper.png", assembly);
            parallaxview.Content = image;
            parallaxview.Speed = 0.5;
            listview.ItemsSource = viewmodel.Items;
            parallaxview.Source = listview;
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Orientation 

The orientation of the content scrolling can be customized to vertical or horizontal using the value of `Orientation` property.

{% tabs %}

{% highlight xaml %}

        <Grid>
          <parallax:SfParallaxView Source="{x:Reference Name = listview}" x:Name="parallaxview" Orientation="Horizontal" >
            <parallax:SfParallaxView.Content>
               
                . . .

            </parallax:SfParallaxView.Content>
          </parallax:SfParallaxView>
     
        <list:SfListView x:Name="listview" Orientation="Horizontal" ItemsSource="{Binding Items}" BackgroundColor="Transparent" ItemSize="100">
               
                    . . .

        </list:SfListView>
        </Grid>
        
{% endhighlight %}

{% highlight c# %}

using Xamarin.Forms;
using Syncfusion.XForms.ParallaxView;

namespace ParallaxView_GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfParallaxView parallaxview = new SfParallaxView();
            Image image = new Image();
            Assembly assembly = typeof(MainPage).GetTypeInfo().Assembly;
            image.Source = ImageSource.FromResource("ParallaxView_GettingStarted.Images.ParallaxWallpaper.png", assembly);
            parallaxview.Content = image;
            parallaxview.Speed = 0.5;
            parallaxview.Orientation = Syncfusion.XForms.ParallaxView.Orientation.Horizontal;
            parallaxview.Source = listview;
        }       
    }
}

{% endhighlight %}
{% endtabs %}