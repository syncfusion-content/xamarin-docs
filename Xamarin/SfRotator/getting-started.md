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

## Add and Configure the SfRotator

You can then add the assembly references to the respective projects as shown below.

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
<td>android\Syncfusion.SfRotator.Android.dll<br/>android\Syncfusion.SfRotator.XForms.Android.dll<br/>android\Syncfusion.SfRotator.XForms.dll<br/> Xamarin.Android.Support.v17.Leanback (from NuGet Packages)</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfRotator.iOS.dll<br/>iOS-unified\Syncfusion.SfRotator.XForms.iOS.dll<br/>iOS-unified\Syncfusion.SfRotator.XForms.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfRotator.UWP.dll<br/>uwp\Syncfusion.SfRotator.XForms.dll<br/>uwp\Syncfusion.SfRotator.XForms.UWP.dll</td>
</tr>
</table>

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

SfRoator provides option to display the navigating items either in Thumbnail or Dots mode. The navigation mode for navigating items can be decided using `NavigationMode` property.

{% tabs %}

{% highlight C# %}	

rotator.NavigationStripMode = NavigationStripMode.Dots;

{% endhighlight %}

{% highlight xaml %}

<rotator:SfRotator x:Name="rotator" NavigationStripMode="Dots" />
	
{% endhighlight %}

{% endtabs %}

## Customizing Position

The placement position of navigation strip items such as Thumbnail or Dots can be customized in SfRotator. This can be specified using `NavigationStripPosition` property.   

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

{% tabs %}

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

{% endtabs %}

Create and populate Rotator collection as follows

{% tabs %}

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

{% endtabs %}

Assigning collection to ItemSource

{% tabs %}

{% highlight C# %}

 rotator.BindingContext = new RotatorViewModel();

{% endhighlight %}

{% endtabs %}

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
