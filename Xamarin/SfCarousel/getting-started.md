---
layout : post
title : Getting Started with Syncfusion Carousel Control for Xamarin.Forms
description : A quick tour to initial users on Syncfusion carousel control for iOS and Xamarin.Forms platform.
platform : Xamarin
control : Carousel
documentation : ug
---

# Getting Started

This section explains you the steps to configure a Carousel control in a real-time scenario and also provides a walk-through on some of the customization features available in Carousel control.

## Creating your first Carousel in Xamarin.Forms

Illustration for the procedures to install the Syncfusion Essential Studio can be refered from [Syncfusion android components installation](http://help.syncfusion.com/xamarin/introduction/download-and-installation#), `Syncfusion.SfCarousel.XForms.aar` should be used to add carousel reference in the application. 

### Referencing Essential Studio components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.
Components/syncfusionessentialstudio-version/lib/pcl/
Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.
After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically
{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib
Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib
Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder
{Download location}\syncfusionessentialstudio-version\lib
You can then add the assembly references to the respective projects as shown below
** PCL Project**
pcl\Syncfusion.SfCaarousel.XForm.dll
** Android Project**

android\Syncfusion. SfCarousel.Andriod.dll
android\Syncfusion. SfCarousel.xForms.Andriod.dll
** IOS (Classic) Project**
iOS\Syncfusion. SfCarousel.iOS.dll
iOS\Syncfusion. SfCarousel.xForms.iOS.dll
iOS\Syncfusion. SfCarousel.XForm.dll
** IOS (Unified) Project**
iOS-unified\Syncfusion.SfCarousel.iOS.dll
iOS-unified\Syncfusion.SfCarousel.xForms.iOS.dll
iOS-unified\Syncfusion.SfCarousel.XForm.dll

Windows Phone Project
wp8\Syncfusion.SfCarousel.WP8.dll
wp8\Syncfusion.SfCarousel.xForms.WinPhone.dll

### Add and Customize the Carousel Control

The Carousel control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a Carousel and configure its elements,

* Create an instance for SfCarousel.

{% highlight C# %}

	SfCarousel sfCarousel=new SfCarousel();

{% endhighlight %}

* Carousel Customization - To enable offset, scale and angle customizations for items, set the values for `Offset`,`ScaleOffset` and `RotationAngle` properties.

{% highlight C# %}	

	//Add list of images name in Array list
	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfCarouselItem item = new SfCarouselItem(this); 
	item.ImageName="image"+i;
	temp.Add(item);
	}
	//Set data source of carousel
	carousel.SelectedIndex=2;
	carousel.DataSource=temp;

	carousel.Offset=20;
	carousel.SelectedItemOffset=0;
	carousel.RotationAngle=40;
	carousel.ScaleOffset=0.7f;

{% endhighlight %}


![](images/gettingstarted.png)

