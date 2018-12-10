---
layout: post
title: Getting Started for Syncfusion Essential Xamarin.Forms SfParallaxView
description: How to create a parallax view, add content and source, speed and orientation.
platform: xamarin.forms
control: SfParallaxView
documentation: ug
---

# Getting Started

This section explains the steps required to configure the [`SfParallaxView`](https://help.syncfusion.com/cr/cref_files/xamarin/sfparallaxview/Syncfusion.SfParallaxView.XForms~Syncfusion.SfParallax.XForms.SfParallaxView.html) control and add basic elements to it using various APIs.

## Adding SfParallaxView reference

Syncfusion components for Xamarin.Forms are available in [nuget.org](https://www.nuget.org/). To add parallax view to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfParallaxView](https://www.nuget.org/packages/Syncfusion.Xamarin.SfParallaxView/), and then install it. 

![SfParallaxView](ParallaxView_Images/parallaxnugetref.png)

To learn more about obtaining Syncfusion components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). If you prefer to manually reference the assemblies instead of NuGet, refer to this [documentation](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfparallaxview) to learn about the dependent assemblies for parallax view.

N> Install the same version of the parallax view in all the projects.

I> If you reference Syncfusion assemblies from the trial setup or NuGet feed, you have to include a license key in your project. Please refer to this [documentation](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your Xamarin application to use our components.

## Launching an application in iOS

To launch the parallax view in iOS, call the `SfParallaxViewRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the LoadApplication method is called as demonstrated in the following code sample.

{% highlight C# %}

    public override bool FinishedLaunching(UIApplication app, NSDictionary options)
    {

        global::Xamarin.Forms.Forms.Init();
        Syncfusion.XForms.iOS.ParallaxView.SfParallaxViewRenderer.Init();
        LoadApplication(new App());

    }

{% endhighlight %}

## Initializing parallax view

1. Import SfParallaxView control namespace as `xmlns:parallax="clr-namespace:Syncfusion.XForms.ParallaxView;assembly=Syncfusion.SfParallaxView.XForms` in the XAML page.

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
        
    public class MainPage : ContentPage
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


## Adding content to the parallax view

### Content

The `Content` represents the background view of a parallax view. You can set any kind of view to the `Content` property such as Image and StackLayout.

The following code sample demonstrates how to set the content property to the parallax view.

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

## Binding source to the parallax view

### Source

The `Source` represents the foreground view of the parallax view. The value of source should be a scrollable content or a view implemented in IParallaxView interface.

As of now, the SfParallaxView supports the following controls directly. You can simply binds these control to the source property, and no further change is required to integrate.

    1. ScrollView
    2. SfListView
    3. SfRotator

The following code sample demonstrates how to bind the SfListView to the `Source` property.

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

N> The size of the `Content` view will automatically be stretched to the size of the `Source` view.

## Customizing the parallax view

### Speed

The `Speed` value denotes the scrolling speed of the `Content` added as a background view. Based on the speed value, the background view will scroll along with the foreground view.

{% highlight xaml %}

     <parallax:SfParallaxView Source="{x:Reference Name = listview}" x:Name="parallaxview" Speed="0.5" >
            <parallax:SfParallaxView.Content>
                <Image BackgroundColor="Transparent" Source="{Binding Image}" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
            </parallax:SfParallaxView.Content>
     </parallax:SfParallaxView>

{% endhighlight %}

### Orientation 

The `Orientation` of the content scrolling can be customized to vertical or horizontal using this property's value.

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

