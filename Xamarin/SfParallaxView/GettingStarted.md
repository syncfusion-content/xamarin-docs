---
layout: post
title: Getting Started for Essential Xamarin.Forms SfParallaxView
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
                <Image x:Name="image" BackgroundColor="Transparent" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
            </parallax:SfParallaxView.Content>
        </parallax:SfParallaxView>       
        </Grid>
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
            image.Source = ImageSource.FromResource("ParallaxSample.ParallaxGuitar1.png", typeof(MainPage).GetTypeInfo().Assembly);
        }
    }
 

{% endhighlight %}
{% endtabs %}

### Source

`Source` represents the foreground view of the parallax view. The value of source should be a scrollable content.

The below code snippet shows how to set the `Source` property value


{% highlight xaml %}

   <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ParallaxSample"
             xmlns:parallax="clr-namespace:Syncfusion.XForms.ParallaxView;assembly=Syncfusion.SfParallaxView.XForms"
             x:Class="ParallaxSample.MainPage">
      
    <ContentPage.Content>
        <Grid>            
        <parallax:SfParallaxView Source="{x:Reference Name = scroll}" x:Name="parallaxview">
            <parallax:SfParallaxView.Content>
                <Image x:Name="image" BackgroundColor="Transparent" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
            </parallax:SfParallaxView.Content>
        </parallax:SfParallaxView>
        <ScrollView x:Name="scroll">
            <StackLayout Spacing="50" VerticalOptions="StartAndExpand">
                <Label Text="Item1" />
                <Label Text="Item2" />
                <Label Text="Item3" />
                <Label Text="Item4" />
                <Label Text="Item5" />
                <Label Text="Item6" />
                <Label Text="Item7" />
                <Label Text="Item8" />
                <Label Text="Item9" />
                <Label Text="Item10" />
                <Label Text="Item11" />
                <Label Text="Item12" />
                <Label Text="Item13" />
                <Label Text="Item14" />
                <Label Text="Item15" />
                <Label Text="Item16" />
                <Label Text="Item17" />
                <Label Text="Item18" />
                <Label Text="Item19" />
            </StackLayout>
        </ScrollView>
        </Grid>
    </ContentPage.Content>
	
    </ContentPage>

{% endhighlight %}

N> `Content` view size automatically stretches to the size of `Source` view.

## Speed

`Speed` value denotes the scrolling speed of `Content` which is added as a background view. Based on the speed value the background view will scroll along with the foreground view.

N>  `Speed` value only applicable for `Content` view. If the speed value set to 0 then the scrolling will be disabled for background view.

{% highlight xaml %}

    <parallax:SfParallaxView Source="{x:Reference Name = scroll}" x:Name="parallaxview" Speed="0.5">
                <parallax:SfParallaxView.Content>
                    <Image x:Name="image" BackgroundColor="Transparent" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
                </parallax:SfParallaxView.Content>
    </parallax:SfParallaxView>

{% endhighlight %}

## Orientation 

`Orientation` of the `Source` and `Content` view can be changed to Vertical or Horizontal using this property value.

{% highlight xaml %}

        <Grid>            
            <parallax:SfParallaxView Source="{x:Reference Name = scroll}" x:Name="parallaxview" Orientation="Vertical">
                <parallax:SfParallaxView.Content>
                    <Image x:Name="image" BackgroundColor="Transparent" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
                </parallax:SfParallaxView.Content>
            </parallax:SfParallaxView>
            <ScrollView x:Name="scroll" Orientation="Vertical">
                <StackLayout Spacing="50" VerticalOptions="StartAndExpand">
                    <Label Text="Item1" />
                    <Label Text="Item2" />
                    <Label Text="Item3" />
                    <Label Text="Item4" />
                    <Label Text="Item5" />
                    <Label Text="Item6" />
                    <Label Text="Item7" />
                    <Label Text="Item8" />
                    <Label Text="Item9" />
                    <Label Text="Item10" />
                    <Label Text="Item11" />
                    <Label Text="Item12" />
                    <Label Text="Item13" />
                    <Label Text="Item14" />
                    <Label Text="Item15" />
                    <Label Text="Item16" />
                    <Label Text="Item17" />
                    <Label Text="Item18" />
                    <Label Text="Item19" />
                </StackLayout>
            </ScrollView>
            </Grid>

        {% endhighlight %}


## ParallaxView support for custom scrollable controls

Parallax view support can obtain for custom scrollable controls with the help of `IParallaxView` interface. This interface implements `ScrollableContentSize` property and `Scrolling` event. 

{% highlight c# %}

    public class CustomScrollview : ScrollView, IParallaxView
        {
            public Size ScrollableContentSize { get => throw new NotImplementedException(); set => throw new NotImplementedException(); }

            public event EventHandler<ParallaxScrollingEventArgs> Scrolling;
        }

{% endhighlight %}

### ScrollableContentSize

`ScrollableContentSize` is the total size of the scrollable custom control.

{% highlight c# %}

 public class CustomScrollview : ScrollView, IParallaxView
    {
        public Size ScrollableContentSize { get; set; }

      public CustomScrollview()
        {
            this.ScrollableContentSize = this.ContentSize;
        }
    }

{% endhighlight %}

### Scrolling event

`Scrolling` event will be triggered whenever the `ParallaxScrollingEventArgs` value has been set through the scrollable custom control scrolled event.

The `ParallaxScrollingEventArgs` has three arguments such as `ScrollX` , `ScrollY` and `CanAnimate` 

* `ScrollX`- It denotes X position of the finished control.

* `ScrollY` - It denotes Y position of the finished scroll.

* `CanAnimate` - It defines whether to animate the scroll or not.

{% tabs %}

{% highlight xaml %}

         <Grid>            
            <parallax:SfParallaxView Source="{x:Reference Name = scroll}" x:Name="parallaxview">
                <parallax:SfParallaxView.Content>
                    <Image x:Name="image" BackgroundColor="Transparent" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
                </parallax:SfParallaxView.Content>
            </parallax:SfParallaxView>
            <local:CustomScrollview x:Name="scroll" Orientation="Horizontal">
                <StackLayout Spacing="50" VerticalOptions="StartAndExpand">
                    <Label Text="Item1" />
                    <Label Text="Item2" />
                    <Label Text="Item3" />
                    <Label Text="Item4" />
                    <Label Text="Item5" />
                    <Label Text="Item6" />
                    <Label Text="Item7" />
                    <Label Text="Item8" />
                    <Label Text="Item9" />
                    <Label Text="Item10" />
                    <Label Text="Item11" />
                    <Label Text="Item12" />
                    <Label Text="Item13" />
                    <Label Text="Item14" />
                    <Label Text="Item15" />
                    <Label Text="Item16" />
                    <Label Text="Item17" />
                    <Label Text="Item18" />
                    <Label Text="Item19" />
                </StackLayout>
            </local:CustomScrollview>
            </Grid>

{% endhighlight %}

{% highlight c# %}

        public class CustomScrollview : ScrollView, IParallaxView
        {
            public Size ScrollableContentSize { get; set; }

            public event EventHandler<ParallaxScrollingEventArgs> Scrolling;

            protected virtual void OnScrollChanged(ParallaxScrollingEventArgs e)
            {
                Scrolling?.Invoke(this, e);
            }

            public CustomScrollview()
            {
                this.Scrolled += CustomScrollview_Scrolled;
                this.ScrollableContentSize = this.ContentSize;
            }

            private void CustomScrollview_Scrolled(object sender, ScrolledEventArgs e)
            {
                OnScrollChanged(new ParallaxScrollingEventArgs(e.ScrollX, e.ScrollY, false));
            }
        }

{% endhighlight %}
{% endtabs %}
