---
layout: post
title: Getting Started for Syncfusion Essential Xamarin.Forms SfParallaxView
description: How to create a parallax view, add content and source, speed and orientation.
platform: xamarin.forms
control: SfParallaxView
documentation: ug
---

# Getting Started

This section explains the steps required to configure the [`SfParallaxView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ParallaxView.SfParallaxView.html) control and add basic elements to it using various APIs.

## Adding SfParallaxView reference

You can add SfParallaxView reference using one of the following methods:

**Method 1: Adding SfParallaxView reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfParallaxView to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfParallaxView](https://www.nuget.org/packages/Syncfusion.Xamarin.SfParallaxView), and then install it.

![Adding SfParallaxView reference from NuGet](ParallaxView_Images/Adding SfParallaxView reference.png)

N> Install the same version of SfParallaxView NuGet in all the projects.

**Method 2: Adding SfParallaxView reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfParallaxView control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfParallaxView assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfParallaxView.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfParallaxView.XForms.Android.dll<br/>Syncfusion.SfParallaxView.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfParallaxView.XForms.iOS.dll<br/>Syncfusion.SfParallaxView.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfParallaxView.XForms.UWP.dll<br/>Syncfusion.SfParallaxView.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

N> If you are adding the references from toolbox, this step is not needed.

## Launch an application in iOS

To launch the parallax view in iOS, call the `SfParallaxViewRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the LoadApplication method is called as demonstrated in the following code sample.

{% highlight C# %}

    public override bool FinishedLaunching(UIApplication app, NSDictionary options)
    {

        global::Xamarin.Forms.Forms.Init();
        Syncfusion.XForms.iOS.ParallaxView.SfParallaxViewRenderer.Init();
        LoadApplication(new App());

    }

{% endhighlight %}

### Universal Windows Platform (UWP)

You need to initialize the parallax view assemblies in App.xaml.cs in UWP project as demonstrated in the following code samples. This is required to deploy the application with parallax view in Release mode in UWP platform.

{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
    {
        …
    	rootFrame.NavigationFailed += OnNavigationFailed;
    
        // Add `using System.Reflection;`
        List<Assembly> assembliesToInclude = new List<Assembly>();
    
        // Now, add all the assemblies your app uses                 
        assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.ParallaxView.SfParallaxViewRenderer).GetTypeInfo().Assembly);
		
        // Replaces Xamarin.Forms.Forms.Init(e);        
        Xamarin.Forms.Forms.Init(e, assembliesToInclude);	
        …     
    }

{% endhighlight %}

### Android

The Android platform does not require any additional configuration to render the parallax view.

## Initialize parallax view

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


## Add content to the parallax view

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

## Bind source to the parallax view

### Source

The `Source` represents the foreground view of the parallax view. The value of `Source` should be a scrollable content or the view which implements IParallaxView interface.

As of now, the SfParallaxView supports the following controls directly. You can simply bind the control to the `Source` property.

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

![SfParallaxView](ParallaxView_Images/parallaxview.gif)

You can find the complete getting started sample from this link: [Sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ParallaxView_GettingStarted979722583.zip )