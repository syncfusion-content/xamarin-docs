---
layout: post
title: Getting Started with Syncfusion TreeMap control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion TreeMap control for Xamarin.Forms platform.
platform: xamarin
control: SfTreeMap
documentation: ug
---

# Getting Started

This section explains you the steps to configure a TreeMap control in a real-time scenario and also provides a walk-through on some of the customization features available in TreeMap control.

## Adding SfTreeMap Reference

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sftreemap) link to know about the assemblies required for adding TreeMap to your project.

Currently an additional step is required for UWP projects. We need to create an instance of the TreeMap custom renderer as shown below.

Create an instance of SfTreeMapRenderer in MainPage constructor of the UWP project as shown

{% highlight C# %}  

public MainPage()
{

    new SfTreeMapRenderer ();

    ...    

}

{% endhighlight %}

   
Create an instance of the SfTreeMapRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as follows.

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

{% tabs %}  

{% highlight xaml %}

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

{% endtabs %}  

## Populating TreeMap Items

The TreeMap accepts a collection of TreeMapItems as input.

{% tabs %}  

{% highlight xaml %}

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

{% endtabs %}  

## Grouping of TreeMap Items using Levels

You can group TreeMapItems using two types of levels.

1. TreeMap Flat Level
2. TreeMap Hierarchical Level

## Customize TreeMap Appearance by Range

You can differentiate the nodes based on its value and color ranges using the Range color. You can also define the color value range using the From and To properties. 

{% tabs %}  

{% highlight xaml %}

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

{% endtabs %}  

## LeafItemSetting

You can customize the Leaf level TreeMap items using LeafItem setting. 

{% tabs %}  

{% highlight xaml %}

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

{% endtabs %} 

## Enable Legend

You can set the color value of leaf nodes using the TreeMap Legend. This legend is appropriate only for the TreeMap whose leaf nodes are colored using RangeColorMapping. You can set ShowLegend property value to “True” to make the legend visible.

## Label for Legends

You can customize the labels of the legend items using the LegendLabel property of RangeColorMapping. 

{% tabs %} 

{% highlight xaml %}

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

{% endtabs %}  

![](Getting-Started_images/img2.png)





