---
layout: post
title: Getting Started with syncfusion Rotator control for Xamarin.Forms 
description:  A quick tour to initial users on Syncfusion Rotator control for Xamarin.Forms platform
platform: xamarin 
control: Rotator
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfRotator control in a real-time scenario and also provides a walk-through on some of the customization features available in SfRotator control.

## Referencing Essential Studio Components in Your Solution	

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib


You can then add the assembly references to the respective projects as shown below.

### PCL 

pcl\Syncfusion.SfRotator.XForms.dll

### Android 

android\Syncfusion.SfRotator.Android.dll
android\Syncfusion.SfRotator.XForms.Android.dll
android\Syncfusion.SfRotator.XForms.dll
Xamarin.Android.Support.v17.Leanback (from NuGet Packages)

### iOS 

iOS-unified\Syncfusion.SfRotator.iOS.dll
iOS-unified\Syncfusion.SfRotator.XForms.iOS.dll
iOS-unified\Syncfusion.SfRotator.XForms.dll

### UWP 

uwp\Syncfusion.SfRotator.UWP.dll
uwp\Syncfusion.SfRotator.XForms.dll
uwp\Syncfusion.SfRotator.XForms.UWP.dll

Currently an additional step is required for iOS projects. We need to create an instance of the rotator custom renderer as shown below. 

Create an instance of SfRotatorRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    new SfRotatorRenderer ();
}	

{% endhighlight %}

{% endtabs %}


## Add and Configure the SfRotator

The following steps help to add a SfRotator control through code.

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight C# %}

	using Syncfusion.SfRotator.XForms; 

{% endhighlight %}

{% highlight xaml %}

	<xmlns:rotator="clr-namespace:Syncfusion.SfRotator.XForms;assembly=Syncfusion.SfRotator.XForms"/>
	
{% endhighlight %}

{% endtabs %}


* Now add the SfRotator control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight C# %}		

	SfRotator rotator = new SfRotator();
	this.Content = rotator;
	
{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator"/>
	
{% endhighlight %}

{% endtabs %}

## Setting Navigation Mode

The navigation mode for navigating items can be decided using `NavigationMode` property. The items can be navigated using Thumbnail or Dots.

{% tabs %}

{% highlight C# %}	

	rotator.NavigationStripMode = NavigationStripMode.Dots;

{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationStripMode="Dots" />
	
{% endhighlight %}

{% endtabs %}

## Customizing Position

The placement position of navigation strip items such as Thumbnail or Dots can be specified using `TabStripPosition` property. 

{% tabs %}

{% highlight C# %}	

	rotator.NavigationStripMode = NavigationStripMode.Dots;
	rotator.NavigationStripPosition = NavigationStripPosition.Bottom;
	
{% endhighlight %}

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator" NavigationStripMode="Dots"  NavigationStripPosition="Bottom"/>
	
{% endhighlight %}

{% endtabs %}

## Add Data Collection

SfRotator items can be populated with a collection of image data. This collection includes Arrays, Lists and DataTables. For example you may wants to create a Rotator model with Image as follows.

{% highlight C# %}
	public RotatorModel(string imagestr)
        {
            Image = imagestr;
        }
        private String _image;

        public String Image
        {
            get { return _image; }
            set { _image = value; }
        }

     
{% endhighlight %}

Create and populate Rotator collection as follows

{% highlight C# %}

	public RotatorViewModel()
        {
            ImageCollection.Add(new RotatorModel("movie1.png"));
            ImageCollection.Add(new RotatorModel("movie2.png"));
            ImageCollection.Add(new RotatorModel("movie3.png"));
            ImageCollection.Add(new RotatorModel("movie4.png"));
            ImageCollection.Add(new RotatorModel("movie5.png"));
        }
        private List<RotatorModel> imageCollection = new List<RotatorModel>();

        public List<RotatorModel> ImageCollection
        {
            get { return imageCollection; }
            set { imageCollection = value; }
        }


{% endhighlight %}

Assigning collection to ItemSource

{% highlight C# %}

 		rotator.BindingContext = new RotatorViewModel();

{% endhighlight %}

## Providing Template for Items

ItemTemplate property of SfRotator control is used to customize the contents of SfRotator items.

{% highlight xaml %}

	<rotator:SfRotator x:Name="rotator"  Grid.Row="0" NavigationDelay="2000" ItemsSource="{Binding ImageCollection}" SelectedIndex="2" NavigationDirection="Horizontal" NavigationStripMode="Dots" BackgroundColor="#ececec" NavigationStripPosition="Bottom">
        <rotator:SfRotator.ItemTemplate>
          <DataTemplate>
            <Image  Source="{Binding Image}"/>                   
          </DataTemplate>
        </rotator:SfRotator.ItemTemplate>
      </rotator:SfRotator>
	  
{% endhighlight %}

![](images/rotator.png)
