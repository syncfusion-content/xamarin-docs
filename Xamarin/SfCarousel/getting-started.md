---
layout : post
title : Getting Started with Syncfusion Carousel control for Xamarin.Forms
description : A quick tour to initial users on Syncfusion Carousel control for Xamarin.Forms platform.
platform : Xamarin
control : Carousel
documentation : ug
---

# Getting Started

This section explains you the steps to configure a Carousel control in a real-time scenario and also provides a walk-through on some of the customization features available in Carousel control.

![](images/gettingstarted.png)

## Referencing Essential Studio components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfCarousel.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfCarousel.Android.dll<br/>android\Syncfusion.SfCarousel.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfCarousel.iOS.dll<br/>ios-unified\Syncfusion.SfCarousel.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfCarousel.XForms.dll</td>
</tr>
<tr>
<td>WindowsPhone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfCarousel.XForms.dll<br/>wp8\Syncfusion.SfCarousel.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WindowsPhone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfCarousel.XForms.dll<br/>wp81\Syncfusion.SfCarousel.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfCarousel.XForms.dll<br/>winrt\Syncfusion.SfCarousel.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfCarousel.UWP.dll<br/>uwp\Syncfusion.SfCarousel.XForms.dll<br/>uwp\Syncfusion.SfCarousel.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, WindowsPhone 8.1 and iOS projects. We need to create an instance of the carousel custom renderer as shown below. 

Create an instance of SfCarouselRenderer in MainPage constructor of the Windows Phone and WindowsPhone 8.1  project as shown 

{% highlight C# %}

public MainPage()

{

    new SfCarouselRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfCarouselRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfCarouselRenderer ();

    ...

}	

{% endhighlight %}

## Add and Configure the Carousel

The Carousel control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a Carousel and configure its elements,

* Adding reference to carousel.

{% tabs %}

{% highlight C# %}

	using Syncfusion.SfCarousel.XForms;

{% endhighlight %}

{% highlight xaml %}

	xmlns:carousel="clr-namespace:Syncfusion.SfCarousel.XForms;assembly=Syncfusion.SfCarousel.XForms"

{% endhighlight %}

{% endtabs %}

* Create an instance for SfCarousel.

{% tabs %}

{% highlight C# %}

	SfCarousel carousel=new SfCarousel();
	this.Content=carousel;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel />
	
{% endhighlight %}

{% endtabs %}

## Setting Offset

Set the Offset property to specify the distance between the items in Carousel panel.

{% tabs %}

{% highlight C# %}

	SfCarousel carousel = new SfCarousel();
	carousel.SelectedIndex=2;
	carousel.Offset=20;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" SelectedIndex="2" Offset="20" />
	
{% endhighlight %}

{% endtabs %}


## Setting Rotation Angle

Set the RotationAngle property to decide the angle in which items should be rotated.

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

## Setting ItemsSource

SfCarousel items can be populated with a collection of image datas. You can assign a collection to it. Collections include arrays, Lists and DataTables.

{% tabs %}

{% highlight C# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfCarouselItem item =new SfCarouselItem();
	item.Image="image"+i;
	temp.add(item);
	}
	carousel.ItemsSource=temp;

{% endhighlight %}

{% highlight xaml %}

	<carousel:SfCarousel x:Name="carousel" ItemsSource="temp" />
	
{% endhighlight %}

{% endtabs %}