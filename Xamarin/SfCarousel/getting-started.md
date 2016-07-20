---
layout : post
title : Getting Started with Syncfusion Carousel control for Xamarin.Forms
description : A quick tour to initial users on Syncfusion Carousel control for Xamarin.Forms platform.
platform : Xamarin
control : Carousel
documentation : ug
---

# Getting Started

This section explains how to showcase a Gallery of photos along with a Title using SfCarousel Control.

## Referencing Essential Studio components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below.

{% tabs %}

{% highlight PCL %}

pcl\Syncfusion.SfCarousel.XForms.dll

{% endhighlight %}

{% highlight Android %}

android\Syncfusion.SfCarousel.Android.dll
android\Syncfusion.SfCarousel.XForms.Android.dll
android\Syncfusion.SfCarousel.XForms.dll
Xamarin.Android.Support.v17.Leanback (from NuGet Packages)
	
{% endhighlight %}

{% highlight iOS %}

iOS-unified\Syncfusion.SfCarousel.iOS.dll
iOS-unified\Syncfusion.SfCarousel.XForms.iOS.dll
iOS-unified\Syncfusion.SfCarousel.XForms.dll

{% endhighlight %}

{% highlight Windows Phone %}

**Windows Phone 8**

wp8\Syncfusion.SfCarousel.WP8.dll
wp8\Syncfusion.SfCarousel.XForms.dll
wp8\Syncfusion.SfCarousel.XForms.WinPhone.dll

**Windows Phone 8.1**

wp81\Syncfusion.SfCarousel.WP.dll
wp81\Syncfusion.SfCarousel.XForms.dll
wp81\Syncfusion.SfCarousel.XForms.WinPhone.dll

{% endhighlight %}

{% highlight WinRT %}

winrt\Syncfusion.SfCarousel.WinRT.dll
winrt\Syncfusion.SfCarousel.XForms.dll
winrt\Syncfusion.SfCarousel.XForms.WinRT.dll

{% endhighlight %}

{% highlight UWP %}

uwp\Syncfusion.SfCarousel.UWP.dll
uwp\Syncfusion.SfCarousel.XForms.dll
uwp\Syncfusion.SfCarousel.XForms.UWP.dll

{% endhighlight %}

{% endtabs %}

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the carousel custom renderer as shown below. 

Create an instance of SfCarouselRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1  project as shown 

{% tabs %}

{% highlight C# %}

public MainPage()
{
    new SfCarouselRenderer();
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfCarouselRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below.

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfCarouselRenderer ();
}	

{% endhighlight %}

{% endtabs %}

## Add and Configure the SfCarousel

The SfCarousel control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfCarousel and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight C# %}

	using Syncfusion.SfCarousel.XForms;

{% endhighlight %}

{% highlight xaml %}

	<xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"/>

{% endhighlight %}

{% endtabs %}

* Now add the SfCarousel control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight C# %}

	SfCarousel carousel=new SfCarousel();
	this.Content=carousel;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel"/>
	
{% endhighlight %}

{% endtabs %}


## Set DataSource

SfCarousel items can be populated with a collection of image data. This collection includes Arrays, Lists and DataTables. For example you can create a SfCarousel model as follows.


{% highlight C# %}

	 public CarouselModel(string imagestr)
     {
         Image = imagestr;
     }
     private string _image;

     public string Image
     {
         get { return _image; }
         set { _image = value; }
     }

{% endhighlight %}

Create and populate SfCarousel collection as follows.

{% highlight C# %}

	carousel.DataSource = GetDataSource();
	List<CarouselModel> GetDataSource()
    {
	    List<CarouselModel> list = new List<CarouselModel>();
	    list.Add(new CarouselModel("image1.png"));
        list.Add(new CarouselModel("image2.png"));
	    list.Add(new CarouselModel("image3.png"));
        list.Add(new CarouselModel("image4.png"));
        list.Add(new CarouselModel("image5.png"));	
	    return list;
	}

{% endhighlight %}

## Set ItemTemplate

`ItemTemplate` property of SfCarousel control is used to customize the contents of SfCarousel items.

{% highlight xaml %}

	<local:SamplePage.Resources>
    	<ResourceDictionary>
     	 	<DataTemplate x:Key="itemTemplate">
       	 		<Image Source="{Binding Image}" 
					Aspect="AspectFit"/>
      		</DataTemplate>
    	</ResourceDictionary>
 	 </local:SamplePage.Resources>

	<local:SamplePage.ContentView >
		<carousel:SfCarousel x:Name="carousel"  ItemTemplate="{StaticResource itemTemplate}"    HeightRequest="400" WidthRequest="800" />
	</local:SamplePage.ContentView >


{% endhighlight %}

## Set Offset Between Items

Set the Offset property to specify the distance between the items in SfCarousel panel.

{% tabs %}

{% highlight C# %}

	SfCarousel carousel = new SfCarousel();
	carousel.SelectedIndex=2;
	carousel.Offset=20;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" SelectedIndex="2" Offset="20"/>
	
{% endhighlight %}

{% endtabs %}


## Set Rotation Angle

Set the `RotationAngle` property to decide the angle in which items should be rotated.

{% tabs %}

{% highlight C# %}

	SfCarousel carousel = new SfCarousel();
	carousel.SelectedIndex=2;
	carousel.Offset=20;
	carousel.RotationAngle = 45;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" SelectedIndex="2" Offset="20" RotationAngle="45" />
	
{% endhighlight %}

{% endtabs %}

![](images/gettingstarted.png)