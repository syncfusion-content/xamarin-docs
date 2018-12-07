---
layout: post
title: Getting Started for Syncfusion Essential Xamarin.Forms SfParallaxView
description: How to create a parallax view, add content and source, speed and orientation.
platform: xamarin.forms
control: SfParallaxView
documentation: ug
---

# Getting Started

This section explains the steps required to configure the [`SfParallaxView`](https://help.syncfusion.com/cr/cref_files/xamarin/sfparallaxview/Syncfusion.SfParallaxView.XForms~Syncfusion.SfParallax.XForms.SfParallaxView.html) and add basic elements to it using various APIs.

## Adding parallax view reference

Syncfusion components for Xamarin.Forms are available in [nuget.org](https://www.nuget.org/). To add parallax view to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfParallaxView](https://www.nuget.org/packages/Syncfusion.Xamarin.SfParallaxView/), and then install it. 

![SfParallaxView](ParallaxView_Images/parallaxnugetref.png)

To know more about obtaining Syncfusion components, refer to these links: [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). If you prefer to manually reference the assemblies instead of NuGet, refer to this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfparallaxview) to know about the dependent assemblies for parallax view. 

N> Install the same version of the parallax view in all the projects.

I> If you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the application in iOS

To launch the parallax view in iOS, call the `SfParallaxViewRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the LoadApplication method is called as shown in the following code sample.

{% highlight C# %} 

 public override bool FinishedLaunching(UIApplication app, NSDictionary options) 

 { 
     … 

     global::Xamarin.Forms.Forms.Init();

     Syncfusion.XForms.iOS.ParallaxView.SfParallaxViewRenderer.Init();

     LoadApplication(new App()); 
     …
 }

{% endhighlight %}

## Initializing parallax view

1. Import SfParallaxView control namespace as `xmlns:parallax="clr-namespace:Syncfusion.XForms.ParallaxView;assembly=Syncfusion.SfParallaxView.XForms` in XAML page.

2. Set the SfParallaxView control as content to the ContentPage.

{% tabs %}

{% highlight xaml %}

        <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
        xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
        xmlns:local="clr-namespace:ParallaxSample"
        xmlns:parallax="clr-namespace:Syncfusion.XForms.ParallaxView;assembly=Syncfusion.SfParallaxView.XForms"
        x:Class="ParallaxSample.MainPage">

            <ContentPage.Content>
                <parallax:SfParallaxView />
            </ContentPage.Content>
	
        </ContentPage>


{% endhighlight %}

{% highlight c# %}

    using Syncfusion.XForms.ParallaxView;
    using Xamarin.Forms;

    public class App : Application
        {
            public App()
            {
                MainPage = new ParallaxSample.MainPage();
            }

        }
    Public class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            SfParallaxView parallaxView = new SfParallaxView();
            this.Content = parallaxView;
        }
    }
{% endhighlight %}
{% endtabs %}



## Adding content and source value to the parallax view

### Content

`Content` represent background view of a parallax view.You can set any kind of view to the `Content` property. 

The following code shows how to set content property to the parallax view.

{% tabs %}

{% highlight xaml %}

   <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ParallaxSample"
             xmlns:parallax="clr-namespace:Syncfusion.XForms.ParallaxView;assembly=Syncfusion.SfParallaxView.XForms"
             x:Class="ParallaxSample.MainPage">
      
    <ContentPage.Content>
        <Grid>            
        <parallax:SfParallaxView x:Name="parallaxview">
            <parallax:SfParallaxView.Content>
                <Image Source="{Binding Image}" BackgroundColor="Transparent" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
            </parallax:SfParallaxView.Content>
        </parallax:SfParallaxView>       
        </Grid>
    </ContentPage.Content>
	
    </ContentPage>

{% endhighlight %}

{% highlight c# %}

    using Syncfusion.XForms.ParallaxView;
    using Xamarin.Forms;

     public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            BindingContext = new ParallaxViewModel();
        }
    }

     public class ParallaxViewModel
        {
            public ImageSource Image { get; set; }

            public ParallaxViewModel()
            {
                Image = ImageSource.FromResource("ParallaxSample.ParallaxGuitar1.png", typeof(MainPage).GetTypeInfo().Assembly);
            }
        }    

{% endhighlight %}
{% endtabs %}

### Source

`Source` represents the foreground view of the parallax view. The value of source should be a scrollable content.

The below code snippet shows how to set the `Source` property value

{% tabs %}

{% highlight xaml %}

  <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ParallaxSample"
             xmlns:list="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:parallax="clr-namespace:Syncfusion.XForms.ParallaxView;assembly=Syncfusion.SfParallaxView.XForms"
             x:Class="ParallaxSample.MainPage">
      
    <ContentPage.Content>
        <Grid>
          <parallax:SfParallaxView Source="{x:Reference Name = listview}" x:Name="parallaxview" >
            <parallax:SfParallaxView.Content>
                <Image BackgroundColor="Transparent" Source="{Binding Image}" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
            </parallax:SfParallaxView.Content>
          </parallax:SfParallaxView>
     
            <list:SfListView x:Name="listview" ItemsSource="{Binding Items}" BackgroundColor="Transparent" ItemSize="100">
                <list:SfListView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <Grid Padding="20,0,20,0" RowSpacing="50">                              
                                <StackLayout BackgroundColor="Transparent" Grid.Column="1" Padding="0,0,0,0" VerticalOptions="CenterAndExpand" HorizontalOptions="StartAndExpand" Orientation="Vertical">
                                    <Label HorizontalOptions="Start" TextColor="White" Text="{Binding Name}" Font="25">
                                    </Label>
                                    <Label HorizontalOptions="Start" Text="{Binding Author}" TextColor="White">
                                    </Label>
                                </StackLayout>                               
                            </Grid>
                        </ViewCell>
                    </DataTemplate>
                </list:SfListView.ItemTemplate>
            </list:SfListView>
        </Grid>
    </ContentPage.Content>
	
    </ContentPage>

{% endhighlight %}

{% highlight c# %}

 public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            BindingContext = new ParallaxViewModel();
        }
    }

       public class ParallaxViewModel
    {
        public ImageSource Image { get; set; }

        public ObservableCollection<Contacts> Items { get; set; }
        public ParallaxViewModel()
        {
            Image = ImageSource.FromResource("ParallaxSample.ParallaxGuitar1.png", typeof(MainPage).GetTypeInfo().Assembly);
            Items = new ObservableCollection<Contacts>()
            {
                new Contacts() { Name = "Thriller", Author = "Michael Jackson" },
                new Contacts() { Name = "Like a Prayer", Author = "Madonna" },
                new Contacts() { Name = "When Doves Cry", Author = "Prince" },
                new Contacts() { Name = "I Wanna Dance", Author = "Whitney Houston" },
                new Contacts() { Name = "It’s Gonna Be Me", Author = "N Sync"},
                new Contacts() { Name = "Everybody", Author = "Backstreet Boys"},
                new Contacts() { Name = "Rolling in the Deep", Author = "Adele" },
                new Contacts() { Name = "Don’t Stop Believing", Author = "Journey" },
                new Contacts() { Name = "Billie Jean", Author = "Michael Jackson" },             
                new Contacts() { Name = "Firework", Author = "Katy Perry"},               
                new Contacts() { Name = "Thriller", Author = "Michael Jackson" },
                new Contacts() { Name = "Like a Prayer", Author = "Madonna" },
                new Contacts() { Name = "When Doves Cry", Author = "Prince" },
                new Contacts() { Name = "I Wanna Dance", Author = "Whitney Houston" },
                new Contacts() { Name = "It’s Gonna Be Me", Author = "N Sync" },
                new Contacts() { Name = "Everybody", Author = "Backstreet Boys" },
                new Contacts() { Name = "Rolling in the Deep", Author = "Adele" },
                new Contacts() { Name = "Don’t Stop Believing", Author = "Journey"},
            };
        }
    }

    public class Contacts
    {
        public string Name
        {
            get;
            set;
        }
        public string Author
        {
            get;
            set;
        }
    }

{% endhighlight %}

{% endtabs %}

N> `Content` view size automatically stretches to the size of `Source` view.

## Speed

`Speed` value denotes the scrolling speed of `Content` which is added as a background view. Based on the speed value the background view will scroll along with the foreground view.

N>  `Speed` value only applicable for `Content` view. If the speed value set to 0 then the scrolling will be disabled for background view.

{% highlight xaml %}

     <parallax:SfParallaxView Source="{x:Reference Name = listview}" x:Name="parallaxview" Speed="0.5" >
            <parallax:SfParallaxView.Content>
                <Image BackgroundColor="Transparent" Source="{Binding Image}" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
            </parallax:SfParallaxView.Content>
     </parallax:SfParallaxView>

{% endhighlight %}

## Orientation 

`Orientation` of the `Source` and `Content` view can be changed to Vertical or Horizontal using this property value.

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

