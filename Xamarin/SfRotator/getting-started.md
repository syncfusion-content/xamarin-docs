---
layout: post
title: Getting Started with syncfusion Rotator control for Xamarin.Forms 
description:  A quick tour to initial users on Syncfusion Rotator control for Xamarin.Forms platform
platform: xamarin 
control: Rotator
documentation: ug
---

# Getting Started

This section explains you the steps to configure a Rotator control in a real-time scenario and also provides a walk-through on some of the customization features available in Rotator control.

![](images/rotator.png)

## Referencing Essential Studio Components in Your Solution	

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
<td>pcl\Syncfusion.SfRotator.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfRotator.Android.dll<br/>android\Syncfusion.SfRotator.XForms.Android.dll<br/>android\Syncfusion.SfRotator.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfRotator.iOS.dll<br/>ios-unified\Syncfusion.SfRotator.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfRotator.XForms.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfRotator.UWP.dll<br/>uwp\Syncfusion.SfRotator.XForms.dll<br/>uwp\Syncfusion.SfRotator.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for iOS projects. We need to create an instance of the rotator custom renderer as shown below. 

Create an instance of SfRotatorRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfRotatorRenderer ();

    ...

}	

{% endhighlight %}


## Add and Configure the Rotator

* Adding reference to Rotator.

{% highlight C# %}

	using Com.Syncfusion.SfRotator.XForms; 

{% endhighlight %}


* Create an instance of Rotator.


{% highlight C# %}		

	SfRotator rotator = new SfRotator();
	this.Content = rotator;
	
{% endhighlight %}

## Setting Navigation Mode

The navigation mode for navigating items can be decided using `NavigationMode` property. The items can be navigated using Thumbnail or Dots.

{% highlight C# %}	

	rotator.NavigationStripMode = NavigationStripMode.Dots;

{% endhighlight %}

## Customizing Position

The placement position of navigation strip items such as Thumbnail or Dots can be specified using `TabStripPosition` property. 

{% highlight C# %}	

	rotator.NavigationStripMode = NavigationStripMode.Dots;
	rotator.NavigationStripPosition = NavigationStripPosition.Bottom;
	
{% endhighlight %}

## Setting DataSource

SfRotator items can be populated with a collection of image datas. You can assign a collection to it. Collections include arrays, Lists and DataTables.


{% highlight C# %}

	ArrayList temp=new ArrayList();
	For(int i=1;i<18;i++)
	{
	SfRotatorItem item =new SfRotatorItem ();
	item.ImageName="image"+i;
	temp.add(item);
	}
	rotator.DataSource=temp;

{% endhighlight %}