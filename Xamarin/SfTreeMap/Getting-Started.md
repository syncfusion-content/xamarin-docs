---
layout: post
title: Getting Started | SfTreeMap | Xamarin | Syncfusion
description: getting started
platform: xamarin
control: SfTreeMap
documentation: ug
---

# Getting Started

This section provides a quick overview for working with EssentialTreemap for Xamarin.Forms, with a walk-through the entire process of creating a real world Treemap. The goal of this walk-through is to help you visualize population growth across continents.

You can also download the entire source code of this demo from the following link: [http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/TreeMap_GettingStarted.zip](http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/TreeMap_GettingStarted.zip)

## Reference Essential Studio Components in your solution

When you acquire Essential Studio components through the Xamarin Component Store interface from your IDE, after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component Manager, you need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL Project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside your solution folder:  

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively when you download Essential Studio from Syncfusion.com or through the Xamarin Store web interface, all the assembly references need to be added manually.  

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio\12.2.0.40\lib

Example: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib

Otherwise, after downloading through the Xamarin Store web interface, all the required assemblies can be found in the following folder:

{download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as follows.

### PCL project

XForms\Syncfusion.SfTreeMap.XForms.dll  

### Android project:

Android\Syncfusion. SfTreeMap.Andriod.dll

Android\Syncfusion. SfTreeMap. XForms.Andriod.dll 

### iOS project:

iOS\Syncfusion. SfTreeMap.iOS.dll   

iOS\Syncfusion. SfTreeMap.XForms.iOS.dll

iOS\Syncfusion. SfTreeMap.XForms.dll

### Windows Phone project

wp8\Syncfusion. SfTreeMap.WP8.dll

wp8\Syncfusion SfTreeMap.XForms.WinPhone.dll



N> Essential TreeMap for Xamarin is compatible with Xamarin Forms 1.2.3.6257

Currently an additional step is required for Windows Phone and iOS projects. You need to create an instance of the TreeMap custom renderer as follows.

1.Create an instance of the SfTreeMapRenderer in MainPage constructor in Windows Phone project as follows.

{% highlight C# %}  

public MainPage()
{

    new SfTreeMapRenderer ();

    ...    

}

{% endhighlight %}

   
2.Create an instance of the SfTreeMapRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

{% highlight C# %}  
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{

    ...

    new SfTreeMapRenderer ();

    ...

}

{% endhighlight %}

   
## Initializing the TreeMap

The Treemap control can be configured entirely in C# code or using XAML markup.

The first step is to create a TreeMap object. 



{% highlight xml %}

<?xml version="1.0" encoding="UTF-8"?>

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:local="clr-namespace:Syncfusion.SfTreeMap.XForms;
  assembly=Syncfusion.SfTreeMap.XForms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
  x:Class="TreeMapGettingStarted.Sample" BackgroundColor=”Black”>

<ContentPage.Content >
	<local:SfTreeMap x:Name="treeMap">
</local:SfTreeMap>

</ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

public static Page GetMainPage()
{

SfTreeMap treeMap = new SfTreeMap();

return new ContentPage
{

    BackgroundColor = Color.Black,

    Content = treeMap,

};
}

{% endhighlight %}



## Populating TreeMap Items

The TreeMap accepts a collection of TreeMapItems as input.


{% highlight xml %}

// BindingContext is set for the content page class.

//DataModel model = new DataModel();

//..

//..

//this.BindingContext = model;

<local:SfTreeMap x:Name="treeMap" Items = "{Binding TreeMapItems}">

</local:SfTreeMap>

{% endhighlight %}




{% highlight c# %}

public class DataModel : BindableObject

{

public static readonly BindableProperty TreeMapItemsProperty =

	BindableProperty.Create<DataModel, ObservableCollection<TreeMapItem>>(p => p.TreeMapItems, null, BindingMode.TwoWay, null, null, null, null);



public ObservableCollection<TreeMapItem> TreeMapItems
{

    get { return (ObservableCollection<TreeMapItem>)GetValue(TreeMapItemsProperty); }

    set { SetValue(TreeMapItemsProperty, value); }

}



public DataModel()
{

    this.TreeMapItems = new ObservableCollection<TreeMapItem>();

    TreeMapItems.Add(new TreeMapItem() { Label = "Indonesia", ColorWeight = 3, Weight = 237641326 });

    TreeMapItems.Add(new TreeMapItem() { Label = "Russia", ColorWeight = 2, Weight = 152518015 });

    TreeMapItems.Add(new TreeMapItem() { Label = "United States", ColorWeight = 4, Weight = 315645000 });

    TreeMapItems.Add(new TreeMapItem() { Label = "Mexico", ColorWeight = 2, Weight = 112336538 });

    TreeMapItems.Add(new TreeMapItem() { Label = "Nigeria", ColorWeight = 2, Weight = 170901000 });

    TreeMapItems.Add(new TreeMapItem() { Label = "Egypt", ColorWeight = 1, Weight = 83661000 });

    TreeMapItems.Add(new TreeMapItem() { Label = "Germany", ColorWeight = 1, Weight = 81993000 });

    TreeMapItems.Add(new TreeMapItem() { Label = "France", ColorWeight = 1, Weight = 65605000 });

    TreeMapItems.Add(new TreeMapItem() { Label = "UK", ColorWeight = 1, Weight = 63181775 });

}

}


SfTreeMap treeMap = new SfTreeMap();

DataModel model = new DataModel();

treeMap.Items = model.TreeMapItems;

{% endhighlight %}

## Grouping of TreeMap Items using Levels

You can group TreeMapItems using two types of levels.

1. TreeMap Flat Level
2. TreeMap Hierarchical Level

## Customize TreeMap Appearance by Range

You can differentiate the nodes based on its value and color ranges using the Range color. You can also define the color value range using the From and To properties. 


{% highlight xml %}


<local:SfTreeMap x:Name="treeMap" Items = "{Binding TreeMapItems}">

<local:SfTreeMap.LeafItemColorMapping>
    <local:RangeColorMapping>
        <local:RangeColorMapping.Ranges>
           <local:Range LegendLabel = "1 % Growth" From = "0" To = "1" Color =  "#77D8D8"  />
           <local:Range LegendLabel = "2 % Growth" From = "0" To = "2" Color =  "#AED960"  />
           <local:Range LegendLabel = "3 % Growth" From = "0" To = "3" Color =  "#FFAF51"  />
           <local:Range LegendLabel = "4 % Growth" From = "0" To = "4" Color =  "#F3D240"  />
        </local:RangeColorMapping.Ranges>
    </local:RangeColorMapping> 
</local:SfTreeMap.LeafItemColorMapping>

</local:SfTreeMap>

{% endhighlight %}


{% highlight c# %}

…

…

ObservableCollection<Range> ranges = new ObservableCollection<Range>();
ranges.Add(new Range() { LegendLabel="1 % Growth", From = 0, To = 1, Color = Color.FromHex("#77D8D8") });
ranges.Add(new Range() { LegendLabel = "2 % Growth", From = 0, To = 2, Color = Color.FromHex("#AED960") });
ranges.Add(new Range() { LegendLabel = "3 % Growth", From = 0, To = 3, Color = Color.FromHex("#FFAF51") });
ranges.Add(new Range() { LegendLabel = "4 % Growth", From = 0, To = 4, Color = Color.FromHex("#F3D240") });
treeMap.LeafItemColorMapping = new RangeColorMapping (){ Ranges = ranges };

{% endhighlight %}


## LeafItemSetting

You can customize the Leaf level TreeMap items using LeafItem setting. 

{% highlight xml %}

<local:SfTreeMap x:Name="treeMap" Items = "{Binding TreeMapItems}">

…

<local:SfTreeMap.LeafItemSettings>
        <local: LeafItemSettings BorderWidth=“1" BorderColor=“White"  />
</local:SfTreeMap. LeafItemSettings >

</local:SfTreeMap>

{% endhighlight %}

{% highlight c# %}

…

LeafItemSettings leafSetting = new LeafItemSettings();
leafSetting.BorderWidth = 1;
leafSetting.BorderColor = Color.White;
treeMap.LeafItemSettings = leafSetting;

{% endhighlight %}

## Enable Legend

You can set the color value of leaf nodes using the TreeMap Legend. This legend is appropriate only for the TreeMap whose leaf nodes are colored using RangeColorMapping. You can set ShowLegend property value to “True” to make the legend visible.

## Label for Legends

You can customize the labels of the legend items using the LegendLabel property of RangeColorMapping. 

{% highlight xml %}

<local:SfTreeMap.LegendSettings>
    <local:LegendSettings  ShowLegend ="true" IconSize=“15,15" Size=“350,70"  />
</local:SfTreeMap.LegendSettings>
{% endhighlight %}



{% highlight c# %}
…

LegendSettings legendSettings = new LegendSettings();
legendSettings.ShowLegend= true;
legendSettings.IconSize = new Size(15, 15);
legendSettings.Size = new Size (350, 70);
treeMap.LegendSettings= legendSettings;

{% endhighlight %}

![](Getting-Started_images/img2.png)





